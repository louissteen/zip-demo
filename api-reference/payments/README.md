---
description: "Batch approved bills into payout groups, schedule settlement, and reconcile transactions."
icon: money-bill-transfer
---

# Payments

Payments settle approved [bills](../bills/README.md). A payout is the settlement of one or more bills to a single vendor through one payment method: ACH, wire, check, or virtual card.

The usual sequence is three calls. Create a payout group from a set of approved bill IDs, which groups them by vendor and payment method and applies any open vendor credits. Review the payouts the group returns. Then schedule the group for a funding date, at which point its payouts move from `scheduled` to `processing` and settle according to the method, typically two business days for ACH.

Payout statuses are `scheduled`, `processing`, `paid`, `failed`, and `cancelled`. A failed payout carries the bank's reason in `failure_reason`, usually a closed or incorrect receiving account, which means the vendor's banking details need correcting in [Vendors](../vendors/README.md) before you retry.

Vendor credits live alongside payouts. Record a credit when a vendor owes an amount back from a return, an overbilling, or a rebate, then apply it to an approved bill to reduce what gets paid.

List payment transactions returns the ledger behind the payouts: funding debits, settlements, credits applied, returns, and fees. Use it to reconcile Zip against a bank statement.

Related: [Global Payments](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).
