---
description: "Fiscal calendars, annual versus quarterly budgets, phasing, rollover, and what happens when a period closes."
icon: calendar-range
---

# Budget periods

The period is the window a budget amount applies to. Choosing it well avoids most of the arguments budgets otherwise generate.

## The fiscal calendar

Budgets follow your organization's fiscal calendar, synced from the ERP alongside the other master data. If your fiscal year starts in February, budget quarters start in February.

Where subsidiaries use different fiscal calendars, each budget follows the calendar of its own subsidiary.

## Choosing granularity

{% tabs %}
{% tab title="Annual" %}
One amount for the whole year.

Simplest to maintain, and appropriate for spend that is genuinely lumpy: a single large agency engagement, or a category where one purchase consumes most of the budget.

The downside is that it gives no early signal. A team can spend the whole year's budget in the first quarter without any control firing.
{% endtab %}

{% tab title="Quarterly" %}
Four amounts, one per quarter.

The usual default. It matches how most finance teams reforecast, gives a meaningful checkpoint four times a year, and does not require monthly phasing accuracy.
{% endtab %}

{% tab title="Monthly" %}
Twelve amounts.

Right for recurring, predictable spend such as contractor costs or cloud consumption, where a month over budget is a real signal.

Wrong for lumpy spend, where it produces monthly variances that mean nothing and train people to ignore the alerts.
{% endtab %}
{% endtabs %}

## Phasing

Phasing is how an annual amount is distributed across the smaller periods. Zip supports even phasing, which divides the annual amount equally, and manual phasing, where you enter each period's amount.

Use manual phasing wherever spend is seasonal. Evenly phasing a budget that is really spent in two months produces eleven months of false comfort and one month of false alarm.

## Rollover

Rollover determines what happens to an unspent amount when a period ends.

**No rollover** is the default. Unspent budget expires at period end. This is the standard treatment for opex.

**Rollover** carries the unspent remainder into the next period. Use it where the underlying commitment genuinely spans periods, such as a project budget approved once and spent over eighteen months.

{% hint style="warning" %}
Rollover and commitment interact. If a purchase order is approved in Q3 but billed in Q4, the commitment sits in Q3 while the consumption lands in Q4. Decide with finance whether the budget should be consumed on approval or on billing, and configure consistently. Mixing the two across budgets makes variance reporting unreadable.
{% endhint %}

## Closing a period

When a period closes, the amounts and the consumed figures are frozen for reporting. Late-arriving bills that relate to the closed period post against the current period unless finance re-opens it, which mirrors how the ERP behaves.

Open commitments do not disappear at period close. A PO approved in the closed period and still unbilled continues to carry its commitment into the new one, so the remaining number stays honest.

## Revising a budget mid-period

Reforecasts are normal. Update the amounts for the remaining periods and leave closed periods alone. Every revision is recorded with the author, timestamp, and previous value in the [audit log](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/), which is what an auditor asks for when a budget suddenly accommodates a purchase it previously would not have.
