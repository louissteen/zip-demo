---
description: "Send a branded purchase order to the vendor, amend it with versioning, and close or cancel it when it is done."
icon: paper-plane
---

# Sending and amending POs

A purchase order only does its job once the vendor has it. Zip generates a branded PO document, sends it to the vendor contacts you choose, and keeps every version of that document on the record so you can prove what the vendor was told and when.

## Sending a PO to the vendor

{% stepper %}
{% step %}
## Open the PO and check the terms

Confirm the vendor contacts, the ship-to address, the total, and anything written in **Special instructions**. These are the fields the vendor reads first, and correcting them after sending means issuing a new version.
{% endstep %}

{% step %}
## Select Send to vendor

The action is in the header of the [purchase order details](purchase-order-details.md) page. Zip shows the contacts on the vendor record and lets you choose which of them receive the PO.
{% endstep %}

{% step %}
## Add a message if you need one

Anything you write here goes in the email body, not on the PO document itself. Use the document's special instructions for terms the vendor must act on.
{% endstep %}

{% step %}
## Send

**Sent status** changes from **Not sent** to the send date, and the send is recorded in the PO activity history with the recipients and the version that was sent.
{% endstep %}
{% endstepper %}

The PO document carries your organization's logo and details rather than Zip branding. Your administrator configures the template once, and every PO from every subsidiary uses it.

{% hint style="info" %}
Sending is separate from approving. A PO can be fully approved and synced to your ERP while still showing **Not sent**, which is the usual state when a buyer is waiting on a contract signature before releasing the order.
{% endhint %}

## What the vendor sees

Vendors do not need a Zip login to receive a PO, but vendors onboarded to the [vendor portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/) get more than an attachment.

* The email includes the PO number, the total, and a link to the portal.
* In the portal the vendor sees the PO, downloads the PDF, and sees every version issued against that PO number.
* The vendor can upload an invoice against the PO directly, which pre-fills the PO reference and removes the most common cause of a failed match.
* The portal shows the vendor the billed and open amounts, so they can see what remains available before invoicing.

Vendors who are not on the portal receive the PDF and reply by email as normal. Their invoices reach Zip through the [other ingestion routes](../invoices/how-invoices-reach-zip.md).

## Amending a PO

Amend a PO when the commercial terms change: the scope grows, the price moves, the dates shift, or the coding was wrong. Amending keeps the PO number and the link to the original request.

{% stepper %}
{% step %}
## Choose Amend from the overflow menu

The PO opens in an editable state. The fields you can change depend on your permissions and on whether anything has been billed.
{% endstep %}

{% step %}
## Make the change

Increasing the total raises the open balance. Decreasing it below the net billed amount is rejected, because you cannot commit less than you have already been invoiced for.
{% endstep %}

{% step %}
## Submit for approval

Zip re-evaluates the approval chain against the new values. An amendment that crosses a threshold your policy cares about, such as a higher total or a different category, pulls in the approvers that the new values require. An amendment that changes nothing routing depends on may need no approval at all.
{% endstep %}

{% step %}
## Send the new version to the vendor

Approval updates the PO in Zip and in the ERP. It does not tell the vendor. Send the amended PO so the vendor is invoicing against the terms you actually approved.
{% endstep %}
{% endstepper %}

### How versioning works

Every approved amendment creates a new version. The **Version** field on the summary panel shows the current number and its creation date.

* Version numbers increment by one and are never reused.
* Superseded versions stay on the record and stay downloadable. The vendor sees the version history in the portal.
* Invoices and bills matched to the PO stay matched across an amendment. They record the version that was current when they were matched.
* The open balance is always calculated against the current version's total.

{% hint style="warning" %}
Amending a PO the vendor has already invoiced against can change the match result on bills that are still in review. If a bill was flagged as an over-billing and you amend the PO upward to cover it, re-run the match on that bill so the exception clears rather than approving over it.
{% endhint %}

<details>
<summary>Amending coding fields after a bill exists</summary>

Changing department, category, subcategory or GL coding on a PO does not retroactively recode bills that have already been posted to the ERP. Those bills keep the coding they were posted with.

Correct posted bills in the ERP, or through a journal entry, following whatever your finance team's period close rules require. Zip's amendment applies to bills coded from that point forward.

</details>

## Closing and cancelling

Closing and cancelling both stop further billing. They are not the same action and are not interchangeable.

| Action | Use it when | Effect |
| --- | --- | --- |
| **Close** | The purchase is finished, whether or not the full amount was billed. | Removes the remaining open balance from your commitments and stops new matches. The billing history is kept. Can be reopened if your permissions allow. |
| **Cancel** | The purchase is not going ahead at all. | Terminal. The PO is voided and cannot be reopened. Only available when nothing has been billed against it. |

Closing a PO with an open balance releases that commitment, which matters for [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/) and for accrual reporting. Buyers who leave partly billed POs open indefinitely overstate committed spend, so most teams run a periodic sweep of stale open POs.

Tell the vendor when you close or cancel a PO they have been sent. Zip does not notify them automatically, because a close is frequently an internal housekeeping action rather than a commercial one.

For reporting on open commitments and PO cycle time, see [Spend Insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).
