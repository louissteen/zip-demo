---
description: "Subscribe to procurement events, verify delivery signatures, and handle retries and replay."
icon: webhook
---

# Webhooks

Webhooks push Zip events to an HTTPS endpoint you control, so a downstream system reacts to an approval or a payment as it happens instead of polling for it.

Create a subscription with the create webhook subscription endpoint, or in Zip under **Settings**, **Developers**, **Webhooks**. A subscription names one endpoint and the events it should receive.

## Event catalog

| Event | Sent when |
| ----- | --------- |
| `request.created` | A purchase request is created in draft |
| `request.submitted` | A request enters `pending_approval` and its chain is built |
| `request.approved` | The last approver on a request approves |
| `request.rejected` | An approver rejects a request |
| `request.cancelled` | A requester or admin cancels a request |
| `purchase_order.created` | A PO is issued from a request or created standalone |
| `purchase_order.sent` | A PO version is emailed to the vendor |
| `purchase_order.closed` | A PO is closed and its commitment is released |
| `invoice.received` | An invoice is created by upload or by API |
| `invoice.matched` | An invoice reaches a clean match against a PO |
| `invoice.match_exception` | Matching breaches a price, quantity, or receipt tolerance |
| `invoice.returned` | An invoice is returned to the vendor |
| `bill.created` | A matched, coded invoice becomes a bill |
| `bill.approved` | The last approver on a bill approves |
| `bill.rejected` | An approver rejects a bill |
| `bill.paid` | A payout settling the bill reaches `paid` |
| `payout.scheduled` | A payout is scheduled for a funding date |
| `payout.paid` | A payout settles |
| `payout.failed` | A payout is returned or rejected by the bank |
| `vendor.created` | A vendor record is created |
| `vendor.onboarding_completed` | A vendor finishes supplier onboarding and becomes active |
| `vendor_credit.applied` | A vendor credit is applied to a bill |
| `budget.threshold_reached` | Committed spend crosses a budget's warning threshold |

## Payload

Every delivery is a POST with the same envelope. The `data` object holds the full record, in the same shape the matching GET endpoint returns.

```json
{
  "id": "evt_7Fk2Rq9dLp",
  "type": "bill.approved",
  "created_at": "2026-10-03T11:48:19Z",
  "subsidiary": "Acme",
  "data": {
    "id": "bil_7Pm5Zt3cKw",
    "object": "bill",
    "status": "approved",
    "vendor_name": "Efficient Llama Systems",
    "total_amount": { "amount": "12450.00", "currency": "USD" },
    "due_date": "2026-10-30"
  }
}
```

## Delivery and retries

Zip expects a `2xx` response within 10 seconds. Acknowledge first and do the work afterward: a slow handler is treated as a failed delivery.

A non-`2xx` response or a timeout is retried with exponential backoff at roughly 1 minute, 5 minutes, 30 minutes, 2 hours, and 6 hours, for up to 24 hours. After 72 hours of consecutive failures Zip sets the subscription to `disabled` and notifies the account's API administrators.

{% hint style="warning" %}
Deliveries are at least once and are not ordered. Handle the same event arriving twice by keying on the event `id`, and use `created_at` rather than arrival order to decide which of two updates is newer.
{% endhint %}

## Verify the signature

Every delivery carries a `Zip-Signature` header built from the raw request body and the subscription's signing secret, which is returned once when the subscription is created.

```
Zip-Signature: t=1759490899,v1=8a7c0f43d81b6e2a95c4d0f7b31e8ac2d5f6091b74e3c8a0d1f2b3c4d5e6f708
```

Compute HMAC SHA-256 over `{timestamp}.{raw body}` and compare it to `v1` in constant time. Reject any request whose timestamp is more than five minutes old, which stops a captured delivery from being replayed against you.

{% tabs %}
{% tab title="Node" %}
```javascript
const crypto = require("crypto");

function verify(rawBody, header, secret) {
  const parts = Object.fromEntries(
    header.split(",").map((p) => p.split("="))
  );
  const expected = crypto
    .createHmac("sha256", secret)
    .update(`${parts.t}.${rawBody}`)
    .digest("hex");

  const fresh = Math.abs(Date.now() / 1000 - Number(parts.t)) < 300;
  const match = crypto.timingSafeEqual(
    Buffer.from(expected),
    Buffer.from(parts.v1)
  );
  return fresh && match;
}
```
{% endtab %}

{% tab title="Python" %}
```python
import hashlib
import hmac
import time


def verify(raw_body: bytes, header: str, secret: str) -> bool:
    parts = dict(p.split("=", 1) for p in header.split(","))
    signed = f"{parts['t']}.".encode() + raw_body
    expected = hmac.new(secret.encode(), signed, hashlib.sha256).hexdigest()

    fresh = abs(time.time() - int(parts["t"])) < 300
    return fresh and hmac.compare_digest(expected, parts["v1"])
```
{% endtab %}
{% endtabs %}

Verify against the raw bytes of the body. Parsing the JSON and re-serializing it changes the whitespace and the signature will not match.

## Replay

Zip keeps 30 days of deliveries. On the **Webhooks** page, open a subscription, select an event in **Deliveries**, and select **Replay** to send it again to the same endpoint. Replay is useful after you fix a handler bug or restore a downstream system, and it is the fastest way to backfill a gap without a full resync.

To catch up beyond 30 days, walk the list endpoints with `created_after` set to the last event you processed. See [Conventions](conventions.md) for the filter parameters.
