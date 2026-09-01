---
description: "Programmatic access to requests, purchase orders, invoices, bills, payouts, vendors, and budgets in Zip."
icon: code
---

# API Reference

The Zip Procurement API gives you programmatic access to the objects that move through the procurement lifecycle. Raise purchase requests from another system, push invoices in from a scanning provider, read approval state for reporting, or keep a data warehouse in step with Zip.

The API follows the same permission model as the Zip application. A key can only see the subsidiaries, departments, and records that its user or service account is entitled to, so an integration cannot read spend that its owner could not read in the product.

## Base URLs

| Environment | Base URL |
| ----------- | -------- |
| Production | `https://api.zip.com/v1` |
| Sandbox | `https://api.sandbox.zip.com/v1` |

Sandbox holds a separate data set with its own vendors, workflows, and API keys. Build and test against sandbox first: it accepts the same calls, runs the same approval engine, and never moves money.

## Versioning

The major version is part of the path. `v1` will keep working as long as it is supported, and Zip announces at least twelve months of notice before a major version is retired.

Within a version, Zip only makes additive changes: new endpoints, new optional request fields, and new fields on existing responses. Treat new response fields and new enum values as expected, and ignore fields your integration does not recognize. Breaking changes, including removing a field or changing the meaning of one, only happen in a new major version.

## Start here

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Authentication</strong></td><td>Create an API key, set scopes, and send the subsidiary header.</td><td><a href="getting-started/authentication.md">authentication.md</a></td></tr><tr><td><strong>Conventions</strong></td><td>Pagination, filtering, idempotency, rate limits, and the error format.</td><td><a href="getting-started/conventions.md">conventions.md</a></td></tr><tr><td><strong>Webhooks</strong></td><td>Subscribe to events, verify signatures, and handle retries.</td><td><a href="getting-started/webhooks.md">webhooks.md</a></td></tr></tbody></table>

## Resources

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Requests</strong></td><td>Raise purchase requests and read their approval chains.</td><td><a href="requests/README.md">README.md</a></td></tr><tr><td><strong>Purchase Orders</strong></td><td>Issue, amend, send, and close purchase orders.</td><td><a href="purchase-orders/README.md">README.md</a></td></tr><tr><td><strong>Invoices</strong></td><td>Upload vendor invoices, match them to a PO, and code them.</td><td><a href="invoices/README.md">README.md</a></td></tr><tr><td><strong>Bills</strong></td><td>Read payables and record approval decisions.</td><td><a href="bills/README.md">README.md</a></td></tr><tr><td><strong>Payments</strong></td><td>Batch bills into payout groups and schedule settlement.</td><td><a href="payments/README.md">README.md</a></td></tr><tr><td><strong>Vendors</strong></td><td>Manage supplier master data, contacts, and onboarding state.</td><td><a href="vendors/README.md">README.md</a></td></tr><tr><td><strong>Budgets</strong></td><td>Read budget balances and check an amount before it is committed.</td><td><a href="budgets/README.md">README.md</a></td></tr></tbody></table>

{% hint style="info" %}
The API mirrors the process described in [Intake-to-Procure](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/) and [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/). Read those spaces first if you are new to how a request becomes a payment.
{% endhint %}
