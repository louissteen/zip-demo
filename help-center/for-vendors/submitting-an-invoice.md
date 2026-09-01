---
description: "Send an invoice to a customer who uses Zip, match it to a purchase order, and avoid the errors that delay payment."
icon: file-arrow-up
---

# Submitting an invoice

Zip accepts invoices several ways. Whichever you use, quoting the purchase order number is what lets your invoice match automatically and move straight into approval.

<figure><img src="../images/invoice-details.png" alt="An invoice matched to a purchase order in Zip" width="820"></figure>

## Ways to submit

| Method | How it works | Best for |
| ------ | ------------ | -------- |
| Vendor portal | Upload the PDF in the portal | Most vendors, and the fastest to process |
| Email | Send the invoice to the address your customer gave you | Vendors invoicing from an accounting system |
| Customer entry | Your customer keys it in from a PDF you sent | Exceptions only |

## Submitting through the portal

{% stepper %}
{% step %}
## Open Invoices

Sign in to the vendor portal and select **Invoices**, then **Submit invoice**.
{% endstep %}

{% step %}
## Select the purchase order

Choose the PO this invoice bills against. The remaining balance is shown so you can check the amount before you submit.
{% endstep %}

{% step %}
## Upload the invoice

Attach the PDF. Zip scans it and pre-fills the invoice number, dates, amounts and tax.
{% endstep %}

{% step %}
## Check and submit

Correct anything the scan misread, then select **Submit**. The invoice appears in your customer's inbox for coding.
{% endstep %}
{% endstepper %}

## What to put on the invoice

* Your invoice number, unique across everything you send this customer
* The purchase order number
* Invoice date and payment terms
* Line items that match the PO description
* Subtotal, tax and total, stated separately
* Your remittance details

{% hint style="warning" %}
An invoice that omits the PO number cannot match automatically. It goes to a manual queue, which is the most common cause of a late payment.
{% endhint %}

## Why an invoice gets returned

* The amount exceeds the remaining PO balance
* The invoice number duplicates one already submitted
* The PO is closed or cancelled
* Line items do not correspond to what the PO covers
* The invoice is billed to the wrong subsidiary

If your invoice is returned, the reason appears in the portal and in the notification email. Correct it and resubmit rather than sending a second invoice with a new number.

## Related articles

* [Payment status and remittance](payment-status-and-remittance.md)
* [Getting started as a vendor](getting-started-as-a-vendor.md)
* [Invoices in the product documentation](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/invoices/how-invoices-reach-zip)
