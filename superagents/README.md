---
description: "Superagents are agents that action procurement work inside your policy and approval boundaries, with every run recorded."
icon: robot
---

# Superagents

Superagents do procurement work rather than describe it. An agent watches for a trigger, checks the action against your policy, does the work it is permitted to do, and stops for a human at the boundaries you set.

Agents operate on the same objects your team does: purchase requests, purchase orders, invoices, bills, vendor records. They use the same approval chains and the same workflow conditions. An agent cannot reach a record its assigned role could not reach, and it cannot skip an approval step that applies to a human doing the same task.

Every run leaves an audit record: what triggered it, what it read, what it changed, which policy checks ran, and who approved. That record is the reason agents are safe to run against production spend.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Agent types</strong></td><td>The agents Zip ships, what each one watches for, and what it produces.</td><td><a href="agents/agent-types.md">agent-types.md</a></td></tr><tr><td><strong>What an agent can do</strong></td><td>The permission model: roles, scopes, and the actions available to an agent.</td><td><a href="agents/what-an-agent-can-do.md">what-an-agent-can-do.md</a></td></tr><tr><td><strong>Guardrails and approval boundaries</strong></td><td>Thresholds, blocked actions, and the checkpoints where an agent must stop.</td><td><a href="agents/guardrails-and-approvals.md">guardrails-and-approvals.md</a></td></tr><tr><td><strong>Agent runs</strong></td><td>The anatomy of a run and the audit record it produces.</td><td><a href="operations/agent-runs.md">agent-runs.md</a></td></tr><tr><td><strong>Monitoring agent performance</strong></td><td>Accuracy, intervention rate, and when to widen or narrow an agent's scope.</td><td><a href="operations/monitoring-performance.md">monitoring-performance.md</a></td></tr></tbody></table>

{% hint style="info" %}
Superagents action work. [AI Procurement Concierge](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/) answers questions. The policy, data boundary, and evidence layer under both is described in [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).
{% endhint %}
