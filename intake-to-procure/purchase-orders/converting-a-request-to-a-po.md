---
description: "Turn a fully approved purchase request into a purchase order and send it to the vendor."
icon: file-invoice
---

# Convert a request to a purchase order

When a request reaches **Approved**, it is cleared to buy but no commitment exists yet. The purchase order is the commitment. Depending on your configuration, Zip creates the PO automatically or waits for a buyer to issue it.

{% stepper %}
{% step %}
## Open the approved request

From the **Requests** page, open a request in **Approved** status and select **Create PO**. Zip copies the vendor, amount, currency, dates, and accounting coding from the request.
{% endstep %}

{% step %}
## Confirm the vendor record

The PO must point at an active vendor record with a remit-to address. If the vendor is still onboarding, the PO cannot be issued until onboarding completes. See [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).
{% endstep %}

{% step %}
## Build the line items

Enter or adjust lines. Each line carries a description, quantity, unit price, and its own accounting coding if your policy splits spend across cost centers or GL codes. The line total must reconcile to the approved amount, or to within the tolerance your administrators set.
{% endstep %}

{% step %}
## Set the PO type

Choose a standard PO for a one-time purchase or a blanket PO for a spend ceiling drawn down over a period. Blanket POs are the usual choice for services billed monthly.
{% endstep %}

{% step %}
## Issue and send

Select **Issue PO**. Zip assigns a PO number, syncs the PO to your ERP, and sends a branded copy to the vendor by email. The vendor can also view and download it in the [vendor portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/).
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
If the line total exceeds the approved amount by more than the configured tolerance, Zip blocks issuance and returns the request for re-approval at the higher amount. Raise the request amount before building lines rather than after.
{% endhint %}

## Changing an issued PO

Issued POs are changed through a revision, not by editing in place. A revision creates a new version of the PO with the change recorded, re-syncs to the ERP, and sends the vendor an updated copy. Increases that cross an approval threshold re-run the relevant approval steps first.

Common revisions are quantity changes, price corrections, extending the period of a blanket PO, and closing remaining balance early.

<details>

<summary>Why did Zip create the PO without me?</summary>

Auto-creation is a workflow setting, usually applied to categories where the approved request is already a complete instruction, such as renewals of an existing subscription. The activity log on the request names the rule that created the PO.

</details>

<details>

<summary>Can one request produce more than one PO?</summary>

Yes. A request that covers several vendors, or a phased purchase, can generate multiple POs. Each PO links back to the same request, and the request tracks the total committed across all of them.

</details>

Once issued, the PO becomes the anchor for receiving, invoice matching, and billing. That part of the lifecycle is covered in [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).
