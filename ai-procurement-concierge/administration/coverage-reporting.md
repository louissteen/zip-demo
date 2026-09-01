---
description: "Measure what AI Procurement Concierge answers, what it deflects, and which policy gaps are generating the most work for your team."
icon: chart-mixed
---

# Coverage reporting

Coverage reporting tells you what share of requester questions the Concierge resolves on its own, and where it does not. Use it to decide what to write down next, not just to report a number upward.

Open **Settings**, then **AI**, then **Concierge**, and select the **Coverage** tab.

## What the report shows

**Answered and deflected.** The split between questions resolved in conversation and questions that became a [handoff](../using-the-concierge/handoff-to-a-human.md), broken out by topic, department, and channel.

**Deflection reasons.** Why each deflection happened: no configured source, conflicting sources, a permissions block, an escalation rule, or a direct request for a person. These reasons lead to different fixes, so read them separately.

**Topics with no source.** Questions asked repeatedly with nothing connected behind them. This is the working list for policy authors.

**Stale sources.** Connected sources past their review date, with the owner named. See [Knowledge sources](knowledge-sources.md).

**Requester feedback.** Answers marked unhelpful, with the question and the sources used, so you can act on them in [Tuning answers](tuning-answers.md).

**Deflected volume by team.** Which teams absorb the handoffs. A single team taking most of them usually means one under-documented process rather than a broadly weak assistant.

## Read the report in this order

{% stepper %}
{% step %}

## Start with volume, not rate

Sort topics by question volume. A topic answered poorly ten times a week matters more than one answered poorly twice a quarter, whatever the percentages say.

{% endstep %}
{% step %}

## Separate gaps from guardrails

A deflection caused by an escalation rule is the system working. Filter those out before you judge coverage, or you will chase a number you deliberately chose.

{% endstep %}
{% step %}

## Fix sources before you tune answers

Where the reason is "no configured source", connect or write the source. Corrections layered over a missing policy do not scale past a handful of topics.

{% endstep %}
{% step %}

## Close the loop with reusable replies

Review the replies your team marked reusable during handoffs and promote the good ones. These are already written in your own language about your own process.

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Do not treat a rising answer rate as an unqualified win. Check it against requester feedback and against the handoffs your team reopens. An assistant answering more questions less accurately moves both numbers in ways that look good in isolation.
{% endhint %}

## Exporting

Export any view as CSV for your own analysis, or read the same measures alongside cycle time and spend in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/). For audit-grade export of AI activity, including the model and prompt version behind each answer, see [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).
