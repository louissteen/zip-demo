---
description: "Create an API key, scope it, send it as a bearer token, and rotate it safely."
icon: key
---

# Authentication

Every call to the Zip Procurement API is authenticated with an API key sent as a bearer token. Calls without a valid key return `401` with an `authentication_error`.

```
Authorization: Bearer zk_live_4a91c0d7f2e84b6ca0135de17a92f4c8
```

Keys are environment specific. A `zk_live_` key works only against `https://api.zip.com/v1`, and a `zk_test_` key works only against `https://api.sandbox.zip.com/v1`.

## Create an API key

{% stepper %}
{% step %}

## Open API keys

In Zip, go to **Settings**, then **Developers**, then **API keys**. You need the **API administrator** permission to see this page.

{% endstep %}
{% step %}

## Create the key

Select **Create key**, give it a name that says which system will use it, and pick the environment. Name keys after the integration, not the person, so ownership survives someone leaving.

{% endstep %}
{% step %}

## Choose scopes

Grant only the scopes the integration needs. Scopes cannot be changed after creation, so a widened integration needs a new key.

{% endstep %}
{% step %}

## Store the secret

The key is shown once. Copy it into your secret manager before closing the dialog. Zip stores only a hash and cannot show it again.

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Treat an API key like a password. Do not commit it to source control, put it in a browser bundle, or paste it into a support ticket. Quote the key's last four characters instead.
{% endhint %}

## Scopes

Scopes are granted per resource and per action. A key that only reads reporting data should never carry a write scope.

| Scope | What it allows |
| ----- | -------------- |
| `requests:read` / `requests:write` | Read purchase requests, create and submit them |
| `purchase_orders:read` / `purchase_orders:write` | Read purchase orders, create, amend, send, and close them |
| `invoices:read` / `invoices:write` | Read invoices, upload, match, code, and return them |
| `bills:read` / `bills:write` | Read bills, approve and reject them |
| `payments:read` / `payments:write` | Read payouts and transactions, create groups and schedule payouts |
| `vendors:read` / `vendors:write` | Read and maintain vendor records and contacts |
| `vendors:pii` | See unmasked tax identifiers and banking details |
| `budgets:read` | Read budgets and run availability checks |
| `webhooks:write` | Manage webhook subscriptions |

A call that needs a scope the key does not carry returns `403` with the code `insufficient_scope`.

## The subsidiary header

Zip is multi-entity. A key can see every subsidiary its owner can see, which means a list call returns records across all of them by default.

Send the optional `X-Zip-Subsidiary` header to scope a call to one entity, using either the subsidiary name or its ID:

```
X-Zip-Subsidiary: Zip Germany
```

Use it on writes as well as reads. Creating a request without the header uses the requester's default subsidiary, which is rarely what a cross-entity integration wants.

## Examples

{% tabs %}
{% tab title="curl" %}
```bash
curl https://api.zip.com/v1/requests?status=pending_approval \
  -H "Authorization: Bearer $ZIP_API_KEY" \
  -H "X-Zip-Subsidiary: Acme"
```
{% endtab %}

{% tab title="Node" %}
```javascript
const res = await fetch(
  "https://api.zip.com/v1/requests?status=pending_approval",
  {
    headers: {
      Authorization: `Bearer ${process.env.ZIP_API_KEY}`,
      "X-Zip-Subsidiary": "Acme",
    },
  }
);

const { data, page_info } = await res.json();
```
{% endtab %}

{% tab title="Python" %}
```python
import os
import requests

res = requests.get(
    "https://api.zip.com/v1/requests",
    params={"status": "pending_approval"},
    headers={
        "Authorization": f"Bearer {os.environ['ZIP_API_KEY']}",
        "X-Zip-Subsidiary": "Acme",
    },
)

payload = res.json()
```
{% endtab %}
{% endtabs %}

## Rotate a key

Rotate on a schedule, and immediately if a key has been exposed.

{% stepper %}
{% step %}

## Create a replacement

Create a second key with the same scopes. Both keys are valid at once, so nothing breaks while you swap.

{% endstep %}
{% step %}

## Deploy the new key

Update your secret manager and roll the change through your services. Watch for `401` responses from anything you missed.

{% endstep %}
{% step %}

## Confirm the old key is idle

On the **API keys** page, check the **Last used** column for the old key. Wait until it has been idle for a full business day.

{% endstep %}
{% step %}

## Revoke the old key

Select **Revoke**. Revocation takes effect within a few seconds and cannot be undone.

{% endstep %}
{% endstepper %}

{% hint style="danger" %}
If a key is leaked, revoke it first and investigate afterward. A revoked key cannot be used, and the audit log keeps every call it made.
{% endhint %}
