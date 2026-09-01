---
description: "Configure thresholds, blocked actions, confidence floors, and the approval boundaries where a Superagent must stop for a human."
icon: shield-halved
---

# Guardrails and approval boundaries

Guardrails decide when an agent proceeds and when it stops. They are evaluated on every action, after role and scope checks pass. Configure them per agent in **Settings**, then **AI**, then **Superagents**.

## Guardrail types

**Amount thresholds.** An agent acts below a value and stops above it. Set thresholds per category as well as globally, because a threshold that is sensible for software renewals is rarely sensible for professional services.

**Confidence floors.** An agent proceeds only when its confidence in the determination clears a floor you set. Below the floor it routes to a human with what it found. Floors are the main control on coding and matching accuracy.

**Variance tolerances.** How far an invoice may differ from its purchase order before the agent stops. Set separately for amount, quantity, and tax.

**Blocked actions.** Actions this agent may never take, regardless of thresholds. Use these for anything your policy says a person owns.

**Novelty rules.** Stop when a situation is new: a vendor with no history, a category the agent has not seen for this department, a first invoice against a new PO.

## Configure a guardrail set

{% stepper %}
{% step %}

## Open the agent

Select the agent, then open the **Guardrails** tab.

{% endstep %}
{% step %}

## Start restrictive

Set thresholds low and confidence floors high for the first cycle. Widening later is a small change. Narrowing after an incident is a conversation with your auditors.

{% endstep %}
{% step %}

## Set the stop behavior

For each guardrail, choose what happens on a stop: route to a named queue, route to the record's existing approver, or hold the item and notify the agent owner.

{% endstep %}
{% step %}

## Test against history

Run the guardrail set in observation mode against recent records. Zip reports what the agent would have done and where it would have stopped, without changing anything.

{% endstep %}
{% step %}

## Enable and review

Turn the agent on, then review stops weekly for the first month. See [Monitoring agent performance](../operations/monitoring-performance.md).

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Observation mode is the only safe way to change a threshold on a live agent. A threshold raised directly in production applies to work already in flight.
{% endhint %}

## Approval boundaries

A guardrail stop is not the same as an approval. A stop hands the item to a person to continue. An approval boundary is a step that a person must complete for the item to progress at all, whether or not an agent was involved.

Approval boundaries come from your existing approval chains. An agent never removes a step, never satisfies one on a person's behalf, and never re-routes around an approver who has not responded. It can prepare the item, attach what the approver needs, and notify them.

For the full picture of where human checkpoints sit in an agent's decision path, see [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/). For how approval chains are built, see the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).
