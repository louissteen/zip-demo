---
description: "Track Superagent accuracy, intervention rate, and reversal rate, and decide when to widen or narrow an agent's scope."
icon: gauge-high
---

# Monitoring agent performance

An agent is worth running when it removes work without adding risk. Both halves need measuring. Open **Superagents**, then **Performance**, and select an agent.

## The measures that matter

**Intervention rate.** The share of runs that stopped for a human. Falling toward zero can mean the agent is doing well, or that your guardrails are too loose to catch anything. Read it next to reversal rate, never alone.

**Reversal rate.** The share of agent actions a human later changed. This is the honest accuracy measure, because it reflects what your team actually disagreed with rather than what the agent believed about itself.

**Stop reasons.** The distribution across thresholds, confidence floors, variance tolerances, and novelty rules. A single reason dominating usually points at one badly set guardrail rather than a broadly cautious agent.

**Time to outcome.** How long records take from trigger to resolution, compared with the same work before the agent was enabled. This is the number to take to your finance leadership.

**Coverage.** The share of eligible records the agent handled at all. An agent scoped so narrowly that it touches a small fraction of volume can post excellent accuracy while saving nobody any time.

## A monthly review

{% stepper %}
{% step %}

## Read reversal rate first

Open the reversed runs and read what the human changed. Cluster them: one vendor, one category, one document format. Clusters are fixable. Scattered reversals usually mean the task needs more judgment than the agent's scope allows.

{% endstep %}
{% step %}

## Check stops against the clusters

If reversals cluster where the agent proceeded confidently, raise the confidence floor for that category rather than the agent overall.

{% endstep %}
{% step %}

## Look for work the agent never saw

Review eligible records the agent skipped. Scope gaps are quieter than errors and usually larger.

{% endstep %}
{% step %}

## Change one thing

Adjust a single guardrail, test it in observation mode, and let it run a full cycle before the next change. See [Guardrails and approval boundaries](../agents/guardrails-and-approvals.md).

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Do not widen an agent's scope and relax its guardrails in the same change. If quality moves, you will not know which one caused it.
{% endhint %}

## When to narrow an agent

Narrow scope when reversals rise on a specific vendor, category, or subsidiary, when a process changes and the agent has not been reconfigured for it, or when the team that owns the reviewed work says the review is taking longer than doing the task themselves. That last signal rarely appears in the numbers and is worth asking about directly.

## Where else these numbers appear

Agent effect on cycle time is visible alongside your other process measures in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/). Model-level quality tracking, including evaluation and drift monitoring across releases, is covered in [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).
