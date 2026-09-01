---
description: "End a vendor relationship cleanly: close open items, revoke access, and retire the record."
icon: box-archive
---

# Offboard a vendor

Offboarding is what stops a dormant vendor from being a liability. An unused vendor record with live bank details, valid system credentials, and a contract that auto-renews is a risk with no offsetting benefit.

{% stepper %}
{% step %}
## Raise the offboarding request

From the vendor record, select **Offboard vendor**. Choose the reason: contract ended, replaced by another supplier, performance, risk or compliance, corporate change, or dormant with no spend. The reason drives which reviewers are added.
{% endstep %}

{% step %}
## Review open commitments

Zip lists open purchase orders, unbilled receipts, unpaid bills, vendor credits, and active contracts. Each must be closed, transferred, or explicitly accepted as an exception before offboarding completes. The vendor moves to **Offboarding** and new purchase orders are blocked.
{% endstep %}

{% step %}
## Serve contract notice

If a contract is still running, check whether notice is required and whether the notice window is open. Serving notice is a task on the offboarding, not an assumption. See [Obligations and renewals](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/).
{% endstep %}

{% step %}
## Complete the exit checklist

The checklist is generated from what the vendor had. Typical items are revoking system and building access, confirming return or deletion of company data with written confirmation, retrieving assets, transitioning services to a replacement supplier, and closing any integration.
{% endstep %}

{% step %}
## Close out finance

Settle outstanding bills, apply or refund vendor credits, close remaining purchase order balances, and confirm no scheduled payments remain. Record the final payment date.
{% endstep %}

{% step %}
## Deactivate the record

When every item is closed, the vendor moves to **Inactive**. Zip disables portal access, blocks new transactions, and syncs the deactivation to your ERP so the vendor cannot be paid from either system.
{% endstep %}
{% endstepper %}

{% hint style="danger" %}
Data return and access revocation are the items most often skipped, because they are owned by teams outside procurement and finance. A vendor whose credentials still work months after the contract ended is an open door. Assign both items to named owners and require evidence rather than a checkbox.
{% endhint %}

## Dormant vendors

Most offboarding candidates are not dramatic exits. They are vendors with no spend for a year or more that nobody has decided about. Run a dormancy report on a schedule, send the list to the vendor owners, and offboard by default rather than keeping records alive on the possibility that someone might use them again.

Reactivation exists and is not expensive. Keeping a dormant vendor active is more expensive than reactivating one you turn out to need.

## What is retained

Deactivation does not delete anything. Transaction history, contracts, tax documents, assessments, and the full change history are retained for the retention period your organization has configured, then archived.

Records are retained because the questions arrive late: a tax authority query about a payment three years ago, a dispute over a service that ended, an audit of who approved a purchase. See [Lifecycle states](lifecycle-states.md) for what archived records still support.

<details>

<summary>Can a vendor be offboarded while a risk finding is open?</summary>

Yes, and it is often the reason for offboarding. Open findings are closed as resolved by termination, with the outcome recorded. Where the finding concerns data the vendor holds, the exit checklist must include confirmed deletion before the finding can be closed. See [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/).

</details>
