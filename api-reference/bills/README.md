---
description: "Read payables, see who has to approve them, and record approval decisions."
icon: file-invoice-dollar
---

# Bills

A bill is the payable. Zip creates it from a matched and coded [invoice](../invoices/README.md), and from that point the record is about money leaving rather than about the vendor's document.

Bills move through `uncoded`, `pending_approval`, `approved`, `paid`, and `rejected`. The approval chain is built the same way a request's chain is, from the amount, subsidiary, and coding on the bill, so finance policy lives in Zip rather than in your integration.

There is no create endpoint here on purpose. A bill only exists because an invoice reached it, which is what keeps the audit trail from the original request through the PO and the invoice to the payment intact.

Approve and reject act on the current step of the chain on behalf of the token's user, so use a key that belongs to a real approver rather than a shared service account when you build an approval surface in another tool. List approvers returns the full chain with each step's state, assignment time, and decision time.

`payable_amount` is what will actually be paid: the total less any applied [vendor credits](../payments/README.md). Once a bill is approved it is eligible for a payout.

For the approval experience in the product, see [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).
