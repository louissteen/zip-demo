---
description: "Pin model and prompt versions for Zip AI features, stage a rollout, and roll back a change that degrades quality."
icon: code-branch
---

# Model and prompt versioning

Every AI feature in Zip runs a versioned combination of a model and a prompt configuration. Both are recorded on every answer and every agent run, so any output can be traced back to the exact version that produced it.

Manage versions in **Settings**, then **AI**, then **Governance**, and open the **Versions** tab.

## What is versioned

**Model version.** The underlying model behind a feature. Zip qualifies new model versions before making them available.

**Prompt configuration.** The instructions, extraction schemas, and output constraints for a feature.

**Tenant configuration.** Your corrections, pinned answers, guardrails, and policy scope. This is versioned separately, because it changes far more often than the model does.

An output is only reproducible when all three are known. That is why the run record carries all three rather than a single label.

## Release channels

**Standard.** Your tenant follows Zip's qualified releases as they ship. Suitable for most customers.

**Pinned.** You hold a named version until you explicitly move. Use this when a validated configuration is part of a control you have attested to.

**Staged.** A new version runs for a subset of entities, categories, or agents while the rest stay on the current version.

{% hint style="info" %}
Pinning is not free. Pinned versions receive quality fixes for a limited window and eventually require a move. Plan a validation cycle rather than pinning indefinitely.
{% endhint %}

## Stage a version change

{% stepper %}
{% step %}

## Review the release notes

Read what changed and which features it touches. Release notes for AI features are published in the [changelog](https://app.gitbook.com/s/PADZ8o5aNtAqqDR0N1py/).

{% endstep %}
{% step %}

## Run the evaluation set

Run your test set against the candidate version before any production traffic reaches it. See [Evaluation and drift](evaluation-and-drift.md).

{% endstep %}
{% step %}

## Stage to a subset

Enable the candidate for one department or one agent. Choose a scope with enough volume to produce a signal within a cycle.

{% endstep %}
{% step %}

## Compare against the holdout

Compare reversal rate, intervention rate, and evaluation scores between the staged group and the group still on the current version.

{% endstep %}
{% step %}

## Promote or roll back

Promote to full scope, or roll back. Rollback restores the previous version for new work and records the reason.

{% endstep %}
{% endstepper %}

## Rollback

Rollback affects new work only. Actions already taken under the previous version stay as they were, because reversing a completed procurement action is a business decision, not a version control operation. The run records for affected work name the version that produced them, so you can find and review the affected set.

<details>
<summary>Finding every output from one version</summary>

Filter agent runs and Concierge answers by version in the AI activity log. This is the query to run after a rollback, and it is the query an auditor asks for when a defect is disclosed. Export is covered in [Compliance evidence](compliance-evidence.md).

</details>
