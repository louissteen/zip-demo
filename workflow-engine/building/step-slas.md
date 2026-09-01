---
description: "Attach response targets to approval steps, choose how the clock runs, and decide what happens when a target is missed."
icon: gauge-high
---

# Step SLAs

An SLA on a step is a response target: how long the assignee has to act once the step activates. SLAs drive reminders, escalation, and the cycle time reporting your procurement team is measured on.

## Set an SLA

{% stepper %}
{% step %}
## Choose the steps to measure

Not every step needs an SLA. Put targets on the steps that gate progress: functional reviews and threshold approvals. Notification steps do not need one.
{% endstep %}

{% step %}
## Set the target

Enter the target duration on the step. Agree it with the team that staffs the queue rather than setting it unilaterally.
{% endstep %}

{% step %}
## Choose the clock

Decide whether the target counts business days or calendar days, and which working calendar applies. For teams spread across regions, pick the calendar of the team responding, not the requester.
{% endstep %}

{% step %}
## Configure what happens on breach

Attach reminders and escalation. See [Escalation and delegation](escalation-and-delegation.md).
{% endstep %}

{% step %}
## Publish and watch the first month

Compare actual response times against the target. Adjust the target to reality before you start reporting on it.
{% endstep %}
{% endstepper %}

## How the clock runs

The clock starts when the step activates, not when the request is submitted. A step sitting behind three earlier approvals is not accruing time.

The clock pauses when the step is waiting on someone else. A step returned to the requester for information stops accruing against the reviewer's target and starts accruing against the requester. This matters: without it, reviewers are penalized for slow requesters and stop asking questions.

Parallel steps each run their own clock, all starting when the parallel block activates.

{% hint style="info" %}
Distinguish step SLA from end-to-end cycle time. Every step can meet its target while a request still takes three weeks, because most elapsed time in a slow chain is spent between steps rather than inside them. Report both. See [Cycle time and bottlenecks](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).
{% endhint %}

## Setting realistic targets

Start from your current performance. Pull the median and the 90th percentile response time for the step over the last quarter, and set the target near the 90th percentile initially. A target that most of the queue already misses produces alert fatigue and gets ignored within a fortnight.

Tighten the target once the queue is consistently inside it.

## Differentiating by risk

A single target across all requests is blunt. Two common refinements:

**Tier by amount.** Low-value requests get a short target, because the review is genuinely quicker. High-value requests get a longer one, because the review is real work.

**Tier by vendor risk.** A vendor already assessed in [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/) needs less time than a new one.

## Common mistakes

**Setting a target on a step with no staffed queue.** The target is missed every time and tells you nothing you did not already know.

**Counting calendar days for a business-hours team.** Every weekend looks like a breach.

**Escalating on the first breach.** Send a reminder first. Escalation should mean something has genuinely gone wrong.
