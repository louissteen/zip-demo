---
description: "Purchase orders, invoices, bills, vendor payments and vendor credits, from an approved request through to a settled payout."
icon: money-bill-transfer
---

# Procure-to-Pay

Procure-to-Pay is the second half of the buying cycle. An approved purchase request becomes a purchase order, the vendor invoices against that PO, the invoice is coded and turned into a bill, the bill is approved, and the bill is paid. Zip holds every one of those objects and keeps them linked, so a payment can always be traced back to the request that started it.

The **Pay** module covers the whole of that path. It scans incoming invoices, matches them to open POs, assigns coders and approvers from your policy, schedules payouts across currencies and subsidiaries, and sends remittance to the vendor. Where you run an ERP, Zip syncs the resulting records to it rather than replacing it.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>What is the Payments Product?</strong></td><td>The features of the Pay module, end to end.</td><td><a href="introduction/what-is-the-payments-product.md">what-is-the-payments-product.md</a></td></tr><tr><td><strong>Purchase orders</strong></td><td>Every field on the PO details page, and what each status means.</td><td><a href="purchase-orders/purchase-order-details.md">purchase-order-details.md</a></td></tr><tr><td><strong>Invoices</strong></td><td>How invoices arrive, get scanned, matched and coded.</td><td><a href="invoices/how-invoices-reach-zip.md">how-invoices-reach-zip.md</a></td></tr><tr><td><strong>Bills</strong></td><td>Approver assignment, review against the PO match, and rejection.</td><td><a href="bills/reviewing-and-approving-bills.md">reviewing-and-approving-bills.md</a></td></tr><tr><td><strong>Vendor payments</strong></td><td>Payout groups, funding, payment methods and remittance.</td><td><a href="vendor-payments/scheduling-payments.md">scheduling-payments.md</a></td></tr><tr><td><strong>Vendor credits</strong></td><td>Credit memos, matching to POs, and paying net of credits.</td><td><a href="vendor-credits/applying-vendor-credits.md">applying-vendor-credits.md</a></td></tr></tbody></table>

{% hint style="info" %}
Everything upstream of the purchase order, including intake forms, approval routing and PO creation, lives in [Intake-to-Procure](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/). For how these objects fit together across the platform, see the [Platform Overview](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/).
{% endhint %}
