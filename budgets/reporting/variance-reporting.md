---
description: "Track budget against commitments and actuals through the period, and explain the differences to finance."
icon: chart-mixed
---

# Variance reporting

Variance reporting answers two questions: where are we against plan, and what is driving the difference. Zip reports on both during the period, not only after it.

## The standard view

The variance view lists budgets as rows and shows, for each:

- The budget amount for the period.
- Consumed, from approved bills.
- Committed, from approved requests and open POs.
- Remaining.
- Variance, as an amount and as a percentage.
- Pipeline, shown separately.

Group by subsidiary, department, category, or budget owner. Grouping by owner is the version to send to the leadership team, because it makes the number somebody's.

## Interpreting the variance

Variance is not automatically a problem. Read committed and consumed together.

**Low consumed, high committed.** Spend has been authorized but not billed. Common early in a period after annual renewals. Not an underspend.

**Low consumed, low committed, late in the period.** A genuine underspend, or a broken mapping. Check the mapping first.

**Consumed close to budget with pipeline outstanding.** The next few approvals will take it over. This is the case worth acting on, and it is the reason pipeline is shown.

{% hint style="info" %}
Compare Zip's consumed figure against the ERP at period end rather than continuously. The two differ during the period by design, because Zip counts approved bills and the ledger counts posted ones. See [How budgets work](../setup/how-budgets-work.md).
{% endhint %}

## Drilling into a variance

Every figure in the view drills through to the records behind it. From a budget's consumed amount you reach the bills; from a bill you reach the invoice, the PO, and the original request with its approval chain.

This is what makes a variance conversation short. The question "what is this 40,000 we did not plan for" is answered by opening the two requests that caused it.

## Unmapped spend

The unmapped view lists approved spend that matched no budget. Review it at least once a period.

Each row is one of three things: a category nobody budgeted for, which needs a budget; a mis-coded request, which needs correcting; or spend that legitimately sits outside budget control, which should be excluded from the view so it stops appearing.

## Sharing the report

Variance views can be saved and scheduled, so budget owners receive their own position without asking for it. See [Scheduled reports and exports](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).

A common cadence is monthly to budget owners, quarterly to finance leadership, and an alert to the owner when a budget crosses its threshold.

## Closing the period

At period close, freeze the view and export it alongside the ERP's actuals. Document the reconciling items, which are usually bills approved but not posted, journals booked outside Zip, and unmapped spend. Doing this once a quarter keeps the differences small and explainable rather than accumulating into an argument at year end.
