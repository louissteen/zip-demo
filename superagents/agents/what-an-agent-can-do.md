---
description: "The Superagent permission model: the role an agent runs as, the scope it operates in, and the actions it is allowed to take."
icon: key
---

# What an agent can do

An agent's authority comes from three things: the role it runs as, the scope it is assigned, and the action list enabled on it. All three are set by an administrator, and an agent can never exceed any of them at run time.

## The role an agent runs as

Every agent runs as a named service role with the same permission model as a human role. If the role cannot see a subsidiary's bills, neither can the agent. This is deliberate: it means you can reason about an agent's reach using the access model you already maintain, rather than a separate one.

Give each agent its own role. A shared role makes the audit trail harder to read and widens every agent when you widen one.

## Scope

Scope narrows the role further, to the set of records the agent may act on.

* Subsidiary or entity
* Department or cost center
* Category and subcategory
* Vendor set, such as approved vendors only
* Amount ceiling per record

An agent evaluates scope on every record before it acts, not once when it starts. A record edited out of scope mid-run stops the run.

## Actions

Actions are enabled individually. Zip groups them by the risk they carry.

**Read actions** retrieve records and documents. Always available within scope.

**Enrich actions** add information without changing a decision: applying a GL code from a matched PO, attaching a prior risk assessment, normalizing a vendor response.

**Progress actions** move an item along a path a human already defined: routing to the next approver, opening a review, requesting a missing document from a vendor.

**Create actions** produce a new record, such as a renewal request or a sourcing package. These are drafts pending human confirmation unless you explicitly allow otherwise.

**Commit actions** change money or identity: approving spend, releasing a payment, changing vendor bank details, awarding a sourcing event.

{% hint style="danger" %}
Commit actions that change vendor bank details or release payment cannot be granted to an agent. Zip blocks them at the platform level rather than leaving them to configuration, because these are the actions payment fraud targets.
{% endhint %}

## How the three combine

At run time, Zip evaluates the role, then the scope, then the action list, then the guardrails described in [Guardrails and approval boundaries](guardrails-and-approvals.md). Every check must pass. A denial at any layer stops the action and records the reason on the run.

<details>
<summary>Agents and delegated approval</summary>

An agent never inherits a human's approval authority, including through delegation. If a step requires an approver, an agent can prepare it, summarize it, and route it, but the approval itself is recorded against a person. This holds even when an administrator has enabled every action available.

</details>

Review each agent's role, scope, and action list on the same cadence you review human access. Both drift the same way, by accumulation.
