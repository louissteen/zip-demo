---
description: "Build payout groups, run multi-currency and multi-subsidiary payment runs, get payouts approved, and send remittance to vendors."
icon: calendar-days
---

# Scheduling payments

Approved bills do not pay themselves. Scheduling is where you decide which approved bills go out, on what date, from which funding source, and who signs off on the run.

<figure><img src="../images/17442008021019-3.png" alt="The Payments page showing total balance, upcoming spend, last month balances, currency tabs and the Ready for payment queue" width="820"></figure>

## The Payments page

Everything to do with paying starts here. The balance cards across the top show the funds available, what is committed, and how the balance moved last month. Currency tabs switch between the currencies you hold, and a subsidiary filter narrows to one entity.

| Tab | What it holds |
| --- | --- |
| **Ready for payment** | Approved bills not yet in a payout group, shown as vendor cards with their amounts. This is where a payment run starts. |
| **Needs approval** | Scheduled payout groups waiting on payout approvers. |
| **Scheduled payments** | Payout groups approved and waiting for their send date. |
| **Transactions** | Individual payment transactions and their status, including returns and failures. |
| **Statements** | Statements for your clearing accounts, by currency. |

**Upcoming spend** splits into **In progress**, meaning payments that have been released and are moving, and **Scheduled**, meaning approved payouts whose send date has not arrived. Read the two together when you are working out how much funding you need in the account.

## Payout groups

A payout group is the unit of scheduling. It bundles bills that will be sent together, approved together, and reported together.

Each group has:

* A **payout group ID** that Zip generates from the send date and currency, for example a date, currency and sequence number
* A **send payment on** date
* A **subsidiary**
* A **funding source**, usually the available balance in your clearing account
* A **count of bills** and a **payout group total**

<figure><img src="../images/17442008021019-4.png" alt="The Schedule payouts page showing the payout group total net of credits, funding needed, send date, funding source, approvers panel and the bills in the group" width="820"></figure>

The **Schedule payouts** page is where you build a group. Select the approved bills to include, set the send date, and add the approvers. The bills table shows priority, invoice number, due date, PO number, vendor, withholding, payment method and amount, and you can filter it by priority, payment method or vendor while you assemble the run.

**Payout group total** is shown net of credits. Hover an amount to see the breakdown: the bill total, any credit applied, and the amount that will actually be paid. See [Applying vendor credits](../vendor-credits/applying-vendor-credits.md).

**Funding needed for urgent bills** and **Available balance for urgent bills** sit side by side so you can see, before you schedule anything, whether the account will cover the run. Funding needed includes fees.

{% hint style="info" %}
Save a group as a draft while you assemble it. **Delete draft** discards it without touching the bills, which return to **Ready for payment**.
{% endhint %}

## Multi-currency and multi-subsidiary runs

You do not need a separate process per currency or per entity. Bills in different currencies and belonging to different subsidiaries can be scheduled in a single payments run.

Zip organizes the run into payout groups behind the scenes, because a payment has to settle in one currency from one funding account. What that means in practice:

* Each payout group is single currency and single subsidiary. The run may contain several.
* Funding is checked per currency, against the balance you hold in that currency.
* Approvals can be set per group, so a subsidiary's controller approves their own entity's payouts.
* Reporting on the run rolls the groups back up, so you see the whole run as one event.

Bills are never converted between currencies to make them fit a group. A bill in GBP is paid in GBP from the GBP balance, matched to a PO raised in GBP.

## The payout approval process

Payout approval is separate from bill approval, and deliberately so. Bill approval says the expense is correct. Payout approval says the money should leave the account now, from this source, to these vendors.

{% stepper %}
{% step %}
## Assemble the group

On the **Ready for payment** tab, select the bills to pay and open **Schedule payouts**. Check the total, the bill count and the funding position.
{% endstep %}

{% step %}
## Set the send date

This is the date Zip releases the payment, not the date the vendor receives it. Settlement time depends on the payment method. Zip defaults the date from the bills' due dates and your terms, so scheduling on the default pays on time rather than early.
{% endstep %}

{% step %}
## Add approvers

The **Approvers** panel lists the approval steps for this group, in order. Your policy pre-populates them from the subsidiary and the amount. Use **Add approver** where an additional sign-off is required, for example on an unusually large run.
{% endstep %}

{% step %}
## Select Schedule payouts

The group moves to **Needs approval**, and the assigned approvers are notified. Nothing is released yet.
{% endstep %}

{% step %}
## Approvers approve the payout

Approvers see the group total, the funding source, the send date and every bill in the group. Once the final approver approves, the group moves to **Scheduled payments**.
{% endstep %}

{% step %}
## The send date arrives

Zip releases the payments automatically using the funding source on the group. No further action is needed.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Approving a payout group does not send the money. The send date does. A group approved well ahead of its send date sits in **Scheduled payments** until that date, which is why the **Scheduled** figure in **Upcoming spend** can be much larger than what is actually moving today.
{% endhint %}

<details>
<summary>Changing or cancelling a scheduled payout</summary>

A group in **Needs approval** can be edited: add or remove bills, change the send date, change the approvers. Editing resets any approvals already given, because approvers approved a different group.

A group in **Scheduled payments** can be cancelled before its send date. The bills return to **Ready for payment** and can be rescheduled. Removing a single bill from an approved group is treated the same way, since the total the approvers signed off on has changed.

Once the send date passes and payments are released, the group cannot be cancelled in Zip. Recovering a released payment means dealing with the bank or with the vendor, and how far you can get depends on the payment method.

</details>

## Combining payments to the same vendor

If your administrators enable it, multiple payments to the same vendor are automatically combined into a single payment carrying only one transaction fee.

Combining applies where the payments share a vendor, a currency, a payment method and a send date. The individual bills stay separate in Zip and in your ERP: only the payment instruction is consolidated. The remittance the vendor receives lists every bill in the combined payment, so their AR team can still apply it correctly.

Where it applies, this reduces both your fees and the number of transactions the vendor has to reconcile.

## Remittance notifications

Zip sends remittance to the vendor automatically when a payment is issued. Vendors do not have to ask, and AP does not have to send anything by hand.

The remittance names the payment amount, the payment date, the payment method, and each bill covered by it with its invoice number and amount. Where a vendor credit was applied, the remittance shows the credit so the vendor can see why the amount differs from the invoice total.

Zip decides where to send it:

| Situation | Where remittance goes |
| --- | --- |
| The vendor has supplied a remittance email address | That address. |
| No remittance email address is on the vendor record | The vendor's first ten contacts. |

{% hint style="info" %}
The fallback to the first ten contacts is a safety net, not a plan. Contacts are ordered as they sit on the vendor record, so remittance can land with a salesperson instead of an AR clerk. Capture a proper remittance address during [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/) and keep it current on the [vendor record](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).
{% endhint %}

Vendors on the [vendor portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/) also see the payment and its remittance detail there, which removes most payment status chasing from your AP inbox.

For where the money comes from and how it moves, see [Funding and payment methods](funding-and-payment-methods.md).
