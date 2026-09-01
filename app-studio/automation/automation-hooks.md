---
description: "Run logic when a record is created, changed, or approved: derive values, validate, call out to other systems, and create related records."
icon: bolt
---

# Automation hooks

An automation hook is logic that runs in response to something happening to a record. Hooks are how a custom object becomes an application rather than a table.

## Anatomy of a hook

Every hook has a trigger, an optional condition, and one or more actions.

**Triggers** fire on record events: created, field changed, status changed, approval step completed, approval chain completed, record deleted. A hook can also run on a schedule, which is the right choice for anything periodic such as expiry checks.

**Conditions** narrow when the actions run, using the same condition grammar as the workflow engine. See [Conditions and branching](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

**Actions** are what happens:

- Set a field on this record, or on a related one.
- Create a related record, such as opening a task or a renewal request.
- Send a notification to a user or group.
- Call an external system through a configured connection.
- Start a workflow.

## Before and after

Hooks run either before the record is saved or after.

**Before-save hooks** can change the values being written and can reject the save with a message. Use them for derivation and validation. Keep them fast: the user is waiting.

**After-save hooks** run once the record is committed. Use them for anything with a side effect outside the record, including notifications, external calls, and creating other records. They cannot block the save.

{% hint style="warning" %}
Do not use a before-save hook to call an external system. If the external system is slow or unavailable, the user cannot save the record and the failure looks like a Zip outage. Call out from an after-save hook and handle the failure there.
{% endhint %}

## Avoiding loops

A hook that writes a field can trigger a hook that watches that field. Zip detects and stops runaway loops, but a stopped loop is a failed automation, not a working one.

Two habits prevent most of it. Scope field-change triggers to the specific fields you care about rather than any change. And when a hook writes back to its own record, add a condition so it does not fire on the value it just wrote.

## Error handling

Actions that fail are recorded on the record's automation history with the error. Configure retry behavior for transient failures such as an external system timing out, and notify an owner for failures that need a human.

A silent automation failure is worse than no automation. Every hook that matters should have a named owner and an alert.

<details>

<summary>Worked example: renewal notice</summary>

**Object**: a `License entitlement` custom object related to a vendor record and a contract.

**Hook 1**, scheduled daily. Condition: renewal date falls within the notice window and no renewal request exists. Actions: create a renewal request pre-filled from the entitlement, and notify the entitlement owner.

**Hook 2**, after-save on the request. Trigger: approval chain completed. Condition: request type is renewal. Action: update the related entitlement with the new term and amount.

The result is a renewal cycle that starts itself and closes its own loop, with both halves visible in the audit log.

</details>

## Permissions and audit

Hooks run under a system identity, not as the user who triggered them, so a hook can update a field the user cannot edit. This is deliberate and is why hook configuration is restricted to administrators.

Every action a hook takes is written to the [audit log](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/) attributed to the automation, so an automated change is never mistaken for a human one.
