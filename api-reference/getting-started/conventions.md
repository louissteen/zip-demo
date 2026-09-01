---
description: "Pagination, filtering, sorting, idempotency keys, rate limits, and the error format."
icon: list-check
---

# Conventions

These rules hold across every endpoint in the API. Learn them once and each resource behaves the way you expect.

## Requests and responses

All request and response bodies are JSON encoded with UTF-8. Send `Content-Type: application/json` on writes, except when you upload an invoice document as multipart form data.

Timestamps are RFC 3339 in UTC, for example `2026-10-01T07:14:38Z`. Plain dates are `YYYY-MM-DD`.

Money is always an object, never a number:

```json
{ "amount": "12450.00", "currency": "USD" }
```

The amount is a string decimal so no precision is lost in transit. Parse it with a decimal type, not a binary float. Supported currencies are USD, EUR, and GBP.

## Pagination

List endpoints return a page of records and a `page_info` object. Paging is cursor based, so a record added while you are paging never shifts the window and causes you to skip a row.

```json
{
  "data": [{ "id": "req_3Nv7Ld9tQz", "object": "request" }],
  "page_info": {
    "has_next_page": true,
    "next_cursor": "eyJvZmZzZXQiOjI1LCJ0cyI6MTc1ODAwMDAwMH0",
    "limit": 25
  }
}
```

Pass `next_cursor` back as the `cursor` parameter to fetch the following page. Stop when `has_next_page` is `false`. `limit` accepts 1 to 100 and defaults to 25.

{% hint style="warning" %}
Cursors are opaque and short lived. Do not decode one, store one for later, or build one yourself. Restart the walk from the first page if a cursor is rejected.
{% endhint %}

## Filtering and sorting

Filters are query parameters named after the field they filter. Repeat a parameter to match several values, which is an OR within that field and an AND across fields:

```
GET /v1/bills?status=pending_approval&status=uncoded&vendor_id=ven_8Kq2Xm4rP1
```

Every list endpoint accepts `created_after` and `created_before` for incremental syncs. Sort with `sort`, which accepts `created_at_desc` (the default), `created_at_asc`, `total_amount_desc`, and `total_amount_asc`.

## Idempotency

Send an `Idempotency-Key` header on any POST that creates or moves money, so a network timeout does not produce a duplicate.

```
Idempotency-Key: 6f1a2b3c-4d5e-4f60-9a71-8b2c3d4e5f60
```

Use a fresh UUID per logical operation. Zip stores the first response for 24 hours and replays it for a repeat of the same key, so a retry returns the original record rather than creating a second one. Reusing a key with a different body returns `400` with the code `idempotency_key_reused`.

## Rate limits

Limits are applied per API key.

| Limit | Value |
| ----- | ----- |
| Sustained | 100 requests per second |
| Burst | 300 requests |
| Invoice uploads | 20 requests per second |
| Bulk reads with `limit=100` | 20 requests per second |

Every response carries `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and `X-RateLimit-Reset`. Exceeding a limit returns `429` with a `Retry-After` header in seconds. Back off exponentially with jitter rather than retrying on a fixed interval.

## Errors

Zip uses standard HTTP status codes and returns the same body shape for every failure.

```json
{
  "type": "validation_error",
  "code": "budget_exceeded",
  "message": "The request exceeds the remaining balance on budget bud_1Qk4Fp7wLv.",
  "param": "line_items[0].amount",
  "request_id": "rq_0a1b2c3d4e5f"
}
```

Branch on `code`, which is stable. `message` is written for humans and changes without notice. Log `request_id` on every failure: support can trace a call in seconds when you quote it.

| Status | `type` | Common `code` values |
| ------ | ------ | -------------------- |
| 400 | `invalid_request_error` | `parameter_invalid`, `parameter_missing`, `idempotency_key_reused` |
| 401 | `authentication_error` | `invalid_api_key`, `api_key_revoked` |
| 403 | `permission_error` | `insufficient_scope`, `subsidiary_not_permitted` |
| 404 | `invalid_request_error` | `resource_missing` |
| 409 | `invalid_state_error` | `invalid_status_transition`, `already_matched`, `po_closed` |
| 413 | `invalid_request_error` | `file_too_large` |
| 422 | `validation_error` | `budget_exceeded`, `vendor_not_onboarded`, `currency_mismatch`, `match_tolerance_breached` |
| 429 | `rate_limit_error` | `rate_limit_exceeded` |
| 500 | `api_error` | `internal_error` |

Retry `429` and `500` responses. Do not retry `400`, `403`, `409`, or `422`: those fail again until you change the request or the record.
