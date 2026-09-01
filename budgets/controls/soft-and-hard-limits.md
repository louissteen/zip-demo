---
description: "Choose whether an over-budget request warns the requester, adds an approval step, or is blocked outright."
icon: shield-halved
---

# Soft and hard limits

Every budget has an enforcement level that decides what happens when a request would take it over. The choice is a policy decision, not a technical one, so make it with finance.

## The three levels

**Warn.** The requester sees that the request takes the budget over, and can submit anyway. The approval chain is unchanged. The over-budget position is recorded and appears in variance reporting.

Use for visibility without friction, and as the starting point for any newly activated budget.

**Require approval.** The request can be submitted, but the workflow adds a budget approval step assigned to the budget owner. The chain does not proceed without it.

This is the right default for most operating budgets. It puts the decision with the person accountable for the number, without stopping the business.

**Block.** The request cannot be submitted while it exceeds the budget. The requester is told which budget is short and by how much, and is pointed at the budget owner.

Use sparingly. Blocking works where the limit is genuinely absolute, such as a capital budget approved by the board, or a grant-funded budget with an external constraint.

{% hint style="warning" %}
Blocking does not stop the spend, it stops the request. People who cannot raise a request buy on a credit card and submit an expense instead, which is worse in every respect. Prefer require approval unless the limit really is absolute.
{% endhint %}

## Thresholds before the limit

Enforcement does not have to wait until the budget is exhausted. Configure a threshold, for example a percentage of the budget consumed, that triggers a notification to the owner.

Threshold alerts give the owner time to reforecast rather than discovering the position when a request is blocked.

## What counts toward the limit

By default the check compares the request amount against remaining, where remaining is the budget less committed less consumed. Pending requests are excluded, so two colleagues can both submit against the same last remaining amount.

You can include pipeline in the check instead. This prevents the double-spend case, at the cost of holding budget for requests that may never be approved. Organizations with long approval cycles and tight budgets usually turn it on; others leave it off.

## Combining with approval thresholds

Budget enforcement and amount thresholds are independent. A request can be under the executive threshold and over budget, and it will pick up the budget approval step without the executive one.

Where both fire, the steps are ordered by the workflow, not by the budget configuration. See [Conditions and branching](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

## Changing the level

Enforcement can be changed at any time and takes effect for new checks. Requests already submitted keep the treatment they received.

Tighten gradually. Moving a budget straight from warn to block in the middle of a period produces a queue of blocked requests and a difficult week for the budget owner. Move to require approval first, watch how many requests trip it, then decide whether blocking is warranted.

Next, see what the requester actually experiences in [Budget checks during intake](budget-checks-in-intake.md).
