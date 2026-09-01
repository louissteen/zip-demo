---
description: "Define what AI may do in Zip per feature, entity, and category, and record who owns each decision."
icon: scale-balanced
---

# AI policy definition

An AI policy in Zip states what each AI feature may do, for which parts of your business, and under whose authority. Policies are set centrally in **Settings**, then **AI**, then **Governance**, and they bind every feature beneath them.

## What a policy contains

**Feature scope.** Which AI features are enabled at all. Features can be off entirely, on in read-only form, or on with actions.

**Entity scope.** Which subsidiaries, regions, and departments the policy applies to. Many customers run different policies per region because their obligations differ.

**Category scope.** Which procurement categories AI may operate in. Categories with regulated or sensitive spend are commonly excluded from action-taking features while remaining in scope for answers.

**Action limits.** The maximum action class available to any agent under this policy. This is a ceiling, not a default. An individual agent can be narrower and never wider. See [what an agent can do](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/).

**Checkpoint requirements.** The decisions that must always involve a person. See [Human checkpoints](human-checkpoints.md).

**Ownership.** The named owner accountable for the policy, and the review date.

## Create a policy

{% stepper %}
{% step %}

## Set the baseline

Start from the most restrictive baseline that still lets a pilot run. Every later change is then an explicit widening with an author and a date against it, which is exactly what an auditor wants to see.

{% endstep %}
{% step %}

## Scope it

Set entity, department, and category scope. Where obligations differ by region, write separate policies rather than one policy with many exceptions.

{% endstep %}
{% step %}

## Set action limits and checkpoints

Choose the highest action class permitted and mark the decisions that always require a person.

{% endstep %}
{% step %}

## Assign an owner and a review date

A policy without a named owner is not maintained. Zip flags policies past their review date.

{% endstep %}
{% step %}

## Publish

Publishing creates a new policy version. The previous version stays available for comparison and for evidence.

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Policy changes apply to work in flight from the moment they publish. Check open agent runs before you narrow a policy, or items mid-run will stop and queue for a human.
{% endhint %}

## Precedence

Where policies overlap, the most restrictive applicable rule wins. An agent configured with a higher action limit than its governing policy permits runs at the policy limit, and the run record notes the reduction.

<details>
<summary>Policy versions and evidence</summary>

Each published version records the author, the timestamp, a diff against the previous version, and the approver if your configuration requires one. Versions are included in the audit export described in [Compliance evidence](../assurance/compliance-evidence.md), so you can show which policy was in force on any given date.

</details>
