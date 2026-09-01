---
description: "Review the record of who changed what in Zip, and export it for internal audit or external attestation."
icon: clipboard-list
---

# Audit log

The audit log is the immutable record of activity across your Zip instance. It captures configuration changes, approval decisions, record edits, and access events. Nothing in the log can be edited or deleted, including by administrators.

## What is captured

**Approval activity**: every approve, reject, request for information, reassignment, delegation, and escalation, with the actor, the timestamp, and any comment.

**Record changes**: field-level changes on requests, POs, invoices, bills, vendor records, and payouts, showing the previous and new values.

**Configuration changes**: edits to intake forms, workflows, budgets, categories, integration settings, and role assignments, including which version was published and by whom.

**Access events**: sign-ins, role grants and removals, SCIM provisioning actions, and API token creation.

## Where to look

Most investigations do not need the global log. Each record carries its own history tab showing the activity for that record in order, which is the fastest way to answer a question about one purchase.

Use the global audit log when the question spans records: who changed the approval threshold last quarter, or what a departing administrator did in their final week.

## Filtering the log

{% stepper %}
{% step %}
## Narrow by time first

Set the date range before anything else. The log is large, and a broad range makes every other filter slower to apply.
{% endstep %}

{% step %}
## Filter by actor or object

Filter by the user who performed the action, or by object type and record ID. Combining both answers most questions in one pass.
{% endstep %}

{% step %}
## Filter by event type

Restrict to configuration changes, approval decisions, or access events depending on what you are checking.
{% endstep %}

{% step %}
## Export the result

Export the filtered set to CSV for the auditor. The export carries the same fields shown on screen, including previous and new values.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Exports reflect the filters applied at the time you run them. Note the filter criteria alongside the file so the sample can be reproduced later.
{% endhint %}

## Reading an entry

Each entry has an actor, an action, an object, a timestamp, and the change itself. Two details are worth understanding:

**System actors are real actors.** Actions taken by an integration, a scheduled job, or an automation appear under a system identity rather than a person. Approvals auto-applied by a rule are labeled as such, so they are distinguishable from a human decision.

**Delegated actions name both parties.** When someone approves on behalf of a delegator, the log records who acted and who they acted for.

## Retention and access

Audit history is retained for the life of the record and is not affected by a user being deactivated. Access to the global log is restricted to administrators; record-level history follows the same visibility rules as the record itself, described in [Roles and permissions](roles-and-permissions.md).

For programmatic access to audit events, see the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).
