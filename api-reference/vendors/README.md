---
description: "Maintain supplier master data, contacts, and onboarding state."
icon: building
---

# Vendors

The vendor record is the supplier master data every other object points at. Requests, purchase orders, invoices, bills, and payouts all carry a `vendor_id`, so the quality of this record decides whether the rest of the process runs cleanly.

A vendor holds the legal and display names, tax identifier, remit-to and billing addresses, default currency, payment terms, payment method, approved categories, and the subsidiaries it is allowed to trade with. Vendors move through `draft`, `onboarding`, `active`, and `inactive`.

Creating a vendor with `send_onboarding_invite` set to true emails the primary contact an invitation to the vendor portal, where the vendor supplies its own tax, banking, and diligence details. That is the intended path: it keeps sensitive data out of your integration and gives you a vendor-attested record.

Changes to banking details, tax identifiers, or the legal name are treated as sensitive. They re-enter supplier onboarding review before they take effect on payments, which is the control that stops a compromised integration from redirecting a payout.

Tax identifiers and banking fields are masked unless the key carries the `vendors:pii` scope. Get onboarding status returns the diligence tasks, their owners, and what the vendor still has to submit.

Related: [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/), [Vendor Portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/).
