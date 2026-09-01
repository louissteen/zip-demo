---
description: "Simulate a workflow against real records, review what would change, and publish without disrupting requests in flight."
icon: vial-circle-check
---

# Test and publish a workflow

Workflows are versioned the same way intake forms are: you edit a draft, and the published version is what live records run. Test before publishing, because a workflow change affects every request submitted afterwards.

## Simulate the draft

{% stepper %}
{% step %}
## Open the simulator

From the workflow draft, select **Simulate**. The simulator builds the chain a record would run without creating anything or notifying anyone.
{% endstep %}

{% step %}
## Choose records to simulate against

Select real historical requests that cover your branches: a low-value request, a software purchase with customer data, a services engagement above the executive threshold, and a renewal.
{% endstep %}

{% step %}
## Read the resulting chain

For each record, the simulator shows the steps that would apply, in order, with the resolved assignee for each and the condition that included or skipped it.
{% endstep %}

{% step %}
## Check every assignee resolves

Look for steps showing an unresolved assignee. These are the ones that stall in production. Add or correct the fallback assignee and simulate again.
{% endstep %}

{% step %}
## Compare against the published version

Use the comparison view to see, for the same records, which steps the published workflow produces and which the draft produces. Every difference should be one you intended.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Simulate against records from more than one subsidiary. Threshold conditions expressed in a single currency are the most common thing that passes testing in the home entity and fails everywhere else.
{% endhint %}

## What to check before publishing

- Every conditional step fires on at least one of your test records, and is skipped on at least one. A step that never fires is dead configuration.
- No step is assigned to a named individual unless that is deliberate.
- Parallel blocks are genuinely parallel, not a sequence you intended to parallelize.
- Self-approval is prevented where policy requires it.
- SLAs and escalation are set on the steps you report on.

## Publish

Select **Publish** and add a note describing the change. The note appears in version history and in the audit log.

Publishing affects new chains only. Requests already in flight continue on the version they started, so an approver mid-chain does not see steps appear or disappear underneath them.

If you need a change to apply to in-flight records, an operator can trigger a recalculation on those records individually. Do this deliberately and only where the policy change is genuinely retroactive.

## Rolling back

Version history lists every publish. Restore an earlier version to make it published again; the restore is recorded as a new version rather than erasing the intervening ones.

## Sequencing with other changes

When a workflow change depends on a new intake field, publish the field first. See [Form versioning](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/). A condition referencing a field that requesters cannot answer yet evaluates as unmatched, so the step silently never fires.

The same ordering applies to changes involving custom objects built in [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/): publish the object and its fields, then the workflow that reads them.
