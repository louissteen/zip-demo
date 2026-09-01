---
description: "Record credit memos from vendors, match them to purchase orders, apply them to coded bills, and pay net of credits."
icon: receipt
---

# Applying vendor credits

When a vendor issues a credit memo, the money is owed back to you. Rather than chasing a refund, Zip lets you apply the credit to bills you are about to pay for that vendor, so the next payment goes out net of the credit.

## What a vendor credit is

A vendor credit is a record of an amount the vendor owes you. It comes from a credit memo the vendor issues, usually for:

* Goods returned or rejected
* An over-billing the vendor has acknowledged
* A service credit under an SLA
* A duplicate invoice the vendor already collected on
* A negotiated rebate or true-up

Credits reach Zip the same ways invoices do: by email to your AP address, by upload in the [vendor portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/), by manual creation on the **Inbox** page, or through the API. Zip scans a credit memo and creates a vendor credit record rather than an invoice, and the document stays attached.

A credit carries a vendor, a currency, an amount, a date, and coding. Like a bill, it syncs to your ERP.

{% hint style="info" %}
A credit memo is not a negative invoice. Record it as a vendor credit. Coding a credit as an invoice with a negative amount breaks PO balances and produces payment instructions your bank will reject.
{% endhint %}

## Matching credits to POs

Where the credit relates to a purchase order, match it to that PO. Matching keeps the PO's numbers honest.

* The credited amount is deducted from **Net billed** on the [purchase order details](../purchase-orders/purchase-order-details.md) page.
* The same amount returns to the PO's **Open** balance, so it can be billed again.
* The credit appears on the PO's **Billing details** tab alongside the bills.

This is why net billed is described as net rather than gross: it is the billed total after credits matched to the PO.

Returning goods that were billed against a PO is the clearest case. The PO committed the spend, the invoice consumed the balance, and the credit gives the balance back so the replacement delivery can be billed against the same PO.

Credits that do not relate to a PO, such as a general rebate, are recorded against the vendor without a PO match. They can still be applied to bills.

## Applying a credit to bills

A credit is applied to coded bills for the same vendor in the same currency. Both conditions are absolute.

{% stepper %}
{% step %}
## Open the vendor credit

Check the amount, the currency, the coding and the remaining unapplied balance. A credit can be applied across several bills, so it may already be partly used.
{% endstep %}

{% step %}
## Choose the bills to apply it to

Zip lists eligible bills: coded, same vendor, same currency, not yet paid. Select the bills you want the credit to reduce.
{% endstep %}

{% step %}
## Set the amount to apply to each bill

You can apply the full credit to one bill or spread it across several. The amount applied to a bill cannot exceed that bill's total, since a bill cannot be paid a negative amount.
{% endstep %}

{% step %}
## Confirm

The credit's unapplied balance drops by the amount applied, and each bill shows the credit against it. The bill's payable amount is now the total less the credit.
{% endstep %}
{% endstepper %}

| Condition | Requirement |
| --- | --- |
| **Vendor** | The credit and the bill must be for the same vendor. |
| **Currency** | The credit and the bill must be in the same currency. No conversion is applied. |
| **Bill state** | The bill must be coded. Uncoded invoices and already-paid bills are not eligible. |
| **Amount** | The applied amount cannot exceed the credit's unapplied balance or the bill's total. |
| **Subsidiary** | Credits apply within the subsidiary that holds the liability. |

<details>
<summary>A credit larger than anything you owe the vendor</summary>

If the credit exceeds the bills available, apply what you can and leave the rest unapplied. The unapplied balance stays on the vendor and is offered again the next time that vendor has an eligible bill.

Where you do not expect further spend with the vendor, for example on offboarding, the remaining balance has to be recovered as a refund from the vendor directly. Zip cannot pay a negative amount, and a credit with no bills to sit against is a receivable, not a payable. Track it as part of [offboarding the vendor](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/lifecycle/offboarding-a-vendor).

</details>

## Paying net of credits

When the bills are scheduled, the payment goes out net of the applied credits.

<figure><img src="../images/17442008021019-4.png" alt="The Schedule payouts page with the payout group total marked net of credits and a bill amount tooltip showing amount to pay, total, and credit applied" width="820"></figure>

On the **Schedule payouts** page, **Payout group total** is labeled **Net of credits**. Hover a bill's amount and the breakdown shows three lines:

* **Amount to pay**, what will actually be sent for that bill
* **Total**, the bill's gross amount
* **Credit applied**, shown as a negative figure

The funding calculation uses the net figure, so a run with credits applied needs less in the clearing account than the gross bill total suggests. See [Funding and payment methods](../vendor-payments/funding-and-payment-methods.md).

{% hint style="warning" %}
Apply credits before the payout group is approved. Applying a credit to a bill that is already in an approved group changes the amount the approvers signed off on, so the group has to be edited and re-approved. Checking for unapplied credits when you assemble the run avoids the rework.
{% endhint %}

## What the vendor sees on the remittance

The remittance Zip sends the vendor shows the credit, not just the reduced number.

For each bill in the payment, the remittance lists the invoice number, the gross amount, any credit applied with its credit memo reference, and the net amount paid. The payment total is the sum of the net amounts.

This matters to the vendor's AR team. A payment that arrives short with no explanation gets logged as a short payment and chased. A remittance that names the credit memo lets them clear both documents in one go.

Vendors on the portal see the same detail there, including which of their credit memos was consumed and how much of it remains unapplied.

For how remittance is addressed and what happens when no remittance email exists, see [Scheduling payments](../vendor-payments/scheduling-payments.md).
