---
description: "Define what counts as managed spend, measure coverage honestly, and use the gap to decide where to expand the process."
icon: bullseye
---

# Spend under management

Spend under management is the share of company spend that went through a defined procurement process. It is the headline coverage metric for most procurement functions, and it is only useful if the definition is written down and held constant.

## Defining it

Agree three things with finance before measuring anything.

**The numerator.** What counts as managed. A common definition is spend on an approved purchase request that ran a procurement review step. Stricter definitions require a purchase order; looser ones count anything that passed through Zip at all.

**The denominator.** Total addressable spend, which is total company spend less what procurement cannot influence. Payroll, taxes, intercompany transfers, and statutory costs are normally excluded.

**The source of truth for the denominator.** Zip does not know about spend that never entered Zip. The denominator comes from the ERP, and the metric is calculated by comparing the two.

{% hint style="warning" %}
A rising number means nothing if the definition moved. Record the definition alongside the figure, and re-state prior periods when you change it.
{% endhint %}

## Measuring it in Zip

The numerator is straightforward: filter approved spend for the period on the criteria in your definition, and total it.

The denominator requires the ERP figure. Most teams export total spend by GL code from the ERP, exclude the out-of-scope accounts, and hold the result alongside the Zip figure in the same view.

Report the metric by subsidiary, by department, and by category. The aggregate number is for the board; the segmented number is what tells you where to work.

## Reading the gap

The interesting output is not the percentage. It is the list of spend that is outside the process, and why.

**A category with no route in.** People are buying something your intake form does not cover. Add the category and a form path.

**A department with low coverage.** Usually a team that has not been onboarded, or one with a local process that predates Zip.

**A subsidiary with low coverage.** Frequently an acquisition still running its own systems.

**High-volume, low-value spend.** Often deliberately outside the process, and reasonably so. Decide whether to bring it in with a lightweight path or exclude it from the denominator explicitly.

**Spend on expense reports that should have been a purchase.** The clearest sign that the request process is too slow or too heavy. Compare against your cycle time. See [Cycle time and bottlenecks](cycle-time-and-bottlenecks.md).

## Improving coverage

Coverage improves by making the managed path easier than the alternative, not by policy alone. The interventions that work are shorter forms, faster approvals, and a landing page that answers the question before it becomes a request. See [The request experience](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).

Where coverage is genuinely a policy problem, the levers are payment controls: requiring a purchase order before an invoice can be paid, and restricting card issuance. Both are configured outside this space, in [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).

## Cadence

Measure quarterly. Monthly measurement produces noise from timing differences between when a request is approved and when the spend posts, and invites arguments about the denominator that are not worth having twelve times a year.
