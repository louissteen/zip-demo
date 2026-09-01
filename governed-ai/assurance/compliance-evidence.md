---
description: "The AI activity record Zip keeps, and how to export evidence for an audit, a security review, or a regulatory assessment."
icon: file-shield
---

# Compliance evidence and audit export

Zip keeps a record of every AI decision, the policy in force at the time, and the human involvement in it. The record exists so that you can answer the question auditors actually ask: what did the system do, under what rules, and who was accountable.

## What is recorded

**Per decision.** The feature, the trigger, the identity it ran as, the context retrieved and the context withheld with reasons, the proposed action, every guardrail evaluated, the outcome, and the model, prompt, and tenant configuration versions in force.

**Per human interaction.** Each checkpoint reached, the reviewer, their decision, any modification they made, and the reason on a rejection. See [Human checkpoints](../policy/human-checkpoints.md).

**Per configuration change.** Policy versions, guardrail changes, boundary changes, corrections, and pinned answers, each with author, timestamp, and a diff.

**Per quality event.** Evaluation runs with their scores and pass or fail result, drift alerts, and version promotions and rollbacks.

Records are immutable. A correction adds a record rather than editing one.

## Export evidence

{% stepper %}
{% step %}

## Open the audit export

Go to **Settings**, then **AI**, then **Governance**, and select **Audit export**.

{% endstep %}
{% step %}

## Set the period and scope

Choose the date range, then the features, entities, and categories in scope. Match the scope to the assessment rather than exporting everything, which makes the evidence pack harder to review.

{% endstep %}
{% step %}

## Choose the level of detail

Summary output gives counts, checkpoint coverage, and configuration changes over the period. Detailed output includes the decision trail for each record in scope.

{% endstep %}
{% step %}

## Generate and download

Zip prepares the export and notifies you when it is ready. Exports are themselves logged, with the requester and the scope.

{% endstep %}
{% endstepper %}

{% hint style="info" %}
Evidence exports are commonly requested during a customer security review as well as an internal audit. Generating one at the start of each quarter is easier than assembling one under a deadline.
{% endhint %}

## Common assessor questions

<details>
<summary>Can AI approve spend on its own?</summary>

No. Approval is always recorded against a person. This is enforced at the platform level and cannot be enabled by configuration. See [what an agent can do](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/).

</details>

<details>
<summary>What data can the models see?</summary>

Only records the acting identity has permission to open, minus the fields excluded at the platform level and any fields your administrator has marked sensitive. Banking details and tax identification numbers are excluded in all cases. See [Data boundaries](../policy/data-boundaries.md).

</details>

<details>
<summary>How do you know an AI decision was correct?</summary>

Each decision carries its evidence and its version. Evaluation sets gate releases, drift monitoring watches for change after release, and reversal rate measures what your own team disagreed with. See [Evaluation and drift](evaluation-and-drift.md).

</details>

<details>
<summary>What happens when a defect is found?</summary>

Filter the activity log by version to identify every affected output, roll back or fix, add the failing cases to the evaluation set, and export the affected set for review. See [Model and prompt versioning](model-and-prompt-versioning.md).

</details>

## Programmatic access

The AI activity record is available through the API for customers who feed evidence into their own governance, risk, and compliance tooling. See the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).
