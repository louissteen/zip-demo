---
description: "Measure how long requests take, separate time in steps from time between them, and find the step that is actually the constraint."
icon: stopwatch
---

# Cycle time and bottlenecks

Cycle time is the metric procurement teams are judged on, and the one most often measured badly. Zip breaks it into parts so that the number points at something you can change.

## The three measures

**End-to-end cycle time** is submission to final approval, or submission to purchase order issued. This is what the business experiences.

**Step duration** is activation to decision, for one step. This is what a review team controls.

**Queue time** is the gap between one step completing and the next activating. It is usually caused by an unresolved assignee, a pending recalculation, or a request returned for information.

The reason to separate them is that end-to-end time is often dominated by queue time, and no amount of pressure on reviewers fixes that.

## Reading the distribution, not the average

Report the median and the 90th percentile, not the mean. Procurement cycle time distributions have a long tail, and the mean is dragged around by a handful of complex requests.

The median tells you what a typical request experiences. The 90th percentile tells you what your unhappiest requesters experienced, which is what they tell everyone else about.

{% hint style="info" %}
Segment before comparing. A software purchase with security, privacy, and legal review is not comparable to a catering order. Segment by category and by whether a contract was involved, then compare like with like.
{% endhint %}

## Finding the bottleneck

<details>

<summary>A workable method</summary>

1. Start with end-to-end time by category. Find the segment that is slowest relative to its volume.
2. Within that segment, break the time down by step. Look at total time contributed, not average duration: a step averaging two days that appears on every request contributes more than a step averaging a week that appears on one in twenty.
3. Split the slow step into step duration and queue time. If queue time dominates, the problem is assignment or recalculation, not the reviewer.
4. For a genuine step duration problem, look at the distribution within the step. A step where most decisions are same-day but a minority take three weeks has a triage problem, not a capacity problem.
5. Check the reassignment and escalation rate on that step. High reassignment means the assignee reference is wrong.

</details>

## Common findings

**The first step is the slowest.** Manager approval often is, because managers are not procurement professionals and the request is not their priority. Reminders and Slack or Teams approvals help more than escalation.

**Sequential reviews that should be parallel.** Check whether legal is genuinely waiting on security. Usually not. See [Approval steps](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

**Time lost to requests for information.** If a step routinely returns requests for missing detail, the intake form is not asking for it. Fix the form rather than the workflow.

**One unstaffed queue.** A single step with no owner can account for most of the tail on its own.

## Making improvement visible

Set a baseline before you change anything, and re-measure the same segment afterwards. Improvements to cycle time are easy to claim and hard to prove, and a baseline saved as a view is the cheapest proof available.

Track step SLA attainment alongside cycle time. Configuration for SLAs is described in [Step SLAs](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).
