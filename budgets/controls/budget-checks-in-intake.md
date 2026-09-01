---
description: "What the requester and the approver see when a request is checked against a budget, and how to resolve a failed check."
icon: magnifying-glass-dollar
---

# Budget checks during intake

The budget check runs while the requester is still filling in the form, and again at submission. Showing the position early is the point: a requester who can see they are over budget before submitting usually talks to the budget owner first.

## When the check runs

**As the form is completed**, once enough dimensions are known to identify a budget. Typically this is after the department, category, and amount have been answered.

**At submission**, as the authoritative check. The result determines whether a budget approval step is added, and is stored on the request.

**On material change**, if the amount increases or the coding changes. See [Conditions and branching](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

## What the requester sees

The budget panel on the form shows the identified budget, the remaining amount, and the position after this request. The wording follows the enforcement level: an informational note for warn, a notice that an approval will be added for require approval, and a blocking message for block.

Requesters are shown the budget name and the owner, not the full budget detail. They do not need to see the whole department's position to decide whether to submit.

{% hint style="info" %}
Requesters frequently ask why a budget they expected was not identified. Nine times out of ten the request is coded to a department or GL code the budget is not mapped to. Check the mapping before assuming the check failed.
{% endhint %}

## What the approver sees

Approvers see the budget position on the request, including remaining before and after, and whether the request is over. The budget owner, when they are the assignee on a budget approval step, additionally sees the pipeline against that budget so they can judge whether approving this request creates a problem for the next one.

## Resolving a failed check

{% stepper %}
{% step %}
## Confirm the coding is right

Check the department, category, and GL code on each line item. A mis-coded line is the most common cause of an unexpected budget result.
{% endstep %}

{% step %}
## Check the amount and currency

Confirm the amount is the full committed value, not a monthly figure, and that the currency is correct. A multi-year contract entered as an annual amount understates the commitment.
{% endstep %}

{% step %}
## Talk to the budget owner

The budget panel names them. Most over-budget requests are resolved by the owner reforecasting or by the requester deferring to the next period.
{% endstep %}

{% step %}
## Reforecast if the budget is genuinely short

The owner revises the amounts for the remaining periods. See [Budget periods](../setup/budget-periods.md). The revision is recorded in the audit log.
{% endstep %}

{% step %}
## Resubmit

Resubmit the request. The check runs again against the revised position.
{% endstep %}
{% endstepper %}

## Requests with no budget

A request that matches no budget passes the check and proceeds normally. It is recorded as unmapped and appears in the unmapped spend view.

This is deliberate: a missing budget should not stop the business. It is also why reviewing unmapped spend matters. See [Variance reporting](../reporting/variance-reporting.md).
