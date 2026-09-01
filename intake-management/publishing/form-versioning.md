---
description: "Draft, publish, and roll back intake form changes without disrupting requests already in flight."
icon: code-compare
---

# Form versioning

Every intake form has a published version that requesters see and a draft you edit. Changes take effect only when you publish, and requests already submitted keep the version they were submitted on.

## The two-version model

**Draft** is your working copy. Editing a draft has no effect on live requesters, so you can leave a half-built change in place indefinitely.

**Published** is what requesters see. Publishing replaces the live version and records the change in the audit log.

**In-flight requests** retain a snapshot of the version they were submitted against. A request submitted last month still displays the questions and answers exactly as they were asked, even after three subsequent publishes.

## Publish a change

{% stepper %}
{% step %}
## Edit the draft

Open the form and make your changes. The editor shows an unpublished changes indicator while a draft differs from the published version.
{% endstep %}

{% step %}
## Review the change summary

Open **Changes** to see the field-level diff between draft and published: fields added, removed, renamed, made required, or made conditional.
{% endstep %}

{% step %}
## Preview each branch

Preview the form and walk the branches your change affects. Confirm that a requester on the most common path still sees a short form.
{% endstep %}

{% step %}
## Publish

Select **Publish**. Add a short note describing what changed and why. The note appears in the version history and in the audit log.
{% endstep %}

{% step %}
## Confirm with a real submission

Submit a test request through the live form and confirm it routes as expected. Withdraw it afterwards.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Removing a field does not remove the answers already given to it. Historical requests keep the answer, but new reports and rules that reference the removed field return nothing. Check your saved views in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/) before removing a field that reporting depends on.
{% endhint %}

## Rolling back

Version history lists every publish with its author, timestamp, and note. Select an earlier version and restore it to make it the published version again. Restoring creates a new version rather than deleting the intervening ones, so the history stays complete.

Roll back when a change causes an immediate problem, such as a required field nobody can answer. For anything less urgent, fix forward: a rollback also reverts changes made by other administrators since.

## Coordinating with workflows

Form changes and workflow changes are versioned separately, and publishing one does not publish the other. When a change spans both, for example a new field that a new approval step branches on, publish in this order:

1. Publish the form field first, so the field exists.
2. Publish the workflow that reads it.

Publishing in the opposite order leaves a workflow condition referencing a field that requesters cannot yet answer, and the condition evaluates as unmatched. See the [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/) for how to test a workflow before publishing.
