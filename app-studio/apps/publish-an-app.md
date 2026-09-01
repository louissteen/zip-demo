---
description: "Release an app to your organization, roll it out to a pilot group first, and maintain it through subsequent versions."
icon: rocket
---

# Publish an app internally

Publishing moves an app from your sandbox into production and makes it available to the users you choose. Apps built in App Studio are internal to your organization; publishing does not expose anything outside it.

## Release the app

{% stepper %}
{% step %}
## Version the app

Set a version and write release notes describing what the app does and what changed. Release notes are shown to administrators and are the record you will rely on when diagnosing behavior six months from now.
{% endstep %}

{% step %}
## Review the release checklist

Zip validates the package before publishing: unresolved references, fields with no layout, hooks with no owner, workflows with unresolved assignees. Clear every item rather than overriding it.
{% endstep %}

{% step %}
## Publish to production

Publish. The objects, fields, layouts, views, hooks, and workflows are created in production. No users have access yet.
{% endstep %}

{% step %}
## Grant access to a pilot group

Assign the app to a small group who agreed to pilot it. Keep the pilot to one team and one use case.
{% endstep %}

{% step %}
## Watch the first two weeks

Check the automation history for failures, the views for records stuck in a status, and the workflow for steps that never fire. Talk to the pilot users rather than reading only the dashboards.
{% endstep %}

{% step %}
## Roll out more widely

Extend access group by group. Announce it where your employees already look, and add an entry point on the intake landing page if requesters need to reach it. See [The request experience](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Publish the data model before the automation that depends on it, and the fields before the workflows that read them. Publishing in the wrong order leaves conditions referencing fields that do not exist yet, and those conditions evaluate as unmatched rather than erroring.
{% endhint %}

## Versioning and rollback

Each publish creates a version. Version history shows what changed, who published it, and when, and the same record appears in the [audit log](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/).

Rolling back reverts configuration, not data. Records created under the newer version stay, along with values in fields the rollback removes from the layout. Plan a rollback as a configuration change with a data consequence, not as an undo.

## Maintaining a published app

**Name an owner.** Every published app needs a person accountable for it, not a team alias. Apps without owners are the ones that break silently.

**Monitor automation failures.** Review the failure history on a regular cadence and alert on repeated failures.

**Review usage.** If nobody has created a record in a quarter, find out whether the process moved elsewhere or the app was never adopted.

**Keep the documentation with the app.** A short description of what the app is for, who owns it, and what its statuses mean saves every future administrator an afternoon.

## Deprecating an app

Deprecate in stages. Stop new record creation first, leaving existing records readable. Communicate the date the app will be removed. Export the records anyone still needs. Then remove the app, which removes its configuration but retains the audit history of what happened while it was live.

Do not remove an app that other configuration still references. Check for workflow conditions, saved views, scheduled reports, and API integrations pointing at its objects before you start.
