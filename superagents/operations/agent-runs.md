---
description: "The anatomy of a Superagent run: trigger, policy check, action, approval, and the audit record it produces."
icon: list-check
---

# Agent runs

A run is one complete pass by an agent over one record, from the trigger that woke it to the audit record it writes. Runs are the unit you monitor, replay, and export.

## The shape of a run

```mermaid
sequenceDiagram
    autonumber
    participant T as Trigger
    participant A as Superagent
    participant P as Policy engine
    participant R as Procurement record
    participant H as Human approver
    participant L as Audit log

    T->>A: Record event (new invoice on PO-4417)
    A->>L: Open run, record trigger and inputs
    A->>R: Read record and related context
    R-->>A: PO, prior coding, vendor history
    A->>P: Request permission for proposed action
    P->>P: Check role, scope, action list, guardrails
    alt Within guardrails
        P-->>A: Allowed
        A->>R: Apply coding and match to PO
        A->>L: Record action and evidence
    else Outside guardrails
        P-->>A: Stopped, threshold exceeded
        A->>L: Record stop and reason
        A->>H: Route with findings attached
        H->>R: Decide and continue
        H->>L: Record decision and approver
    end
    A->>P: Request progression to approval step
    P-->>A: Requires human approval
    A->>H: Notify approver with summary
    H-->>R: Approve
    H->>L: Record approval
    A->>L: Close run with outcome
```

The policy check runs before the action, never after. An agent does not act and then seek forgiveness, because a reversal on a procurement record is not always possible once downstream systems have consumed it.

## What a run record contains

* The trigger: the event, the record, and the timestamp.
* The agent, its version, and the model and prompt version in use. See [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).
* Every record and document read, with the permission check result for each.
* The proposed action and the reasoning summary behind it.
* Every guardrail evaluated and its result, including the ones that passed.
* The action taken, or the stop and its reason.
* Any human decision, with the person, the timestamp, and what they changed.
* The final outcome and the run duration.

## Reviewing runs

Open **Superagents**, then **Runs**. Filter by agent, outcome, record type, or date. Each run opens as a timeline you can read top to bottom.

{% hint style="info" %}
Start with stopped runs rather than completed ones. Stops tell you where your guardrails sit relative to reality. A run that completed as expected rarely teaches you anything.
{% endhint %}

<details>
<summary>Replaying a run</summary>

Select **Replay** on any run to re-evaluate it against the agent's current configuration. Replay reports what the agent would do now and where it would stop, without touching the record. Use replay to confirm the effect of a guardrail change before you apply it, and to check whether a past error is still reachable after a fix.

</details>

## Export

Runs export as structured records for your own analysis or for evidence. The export includes the full decision trail, not just the outcome. See the compliance evidence and audit export guidance in [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/), and the programmatic access described in the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).
