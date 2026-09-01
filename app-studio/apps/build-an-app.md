---
description: "Assemble objects, layouts, views, and automation into an app, then test it in a sandbox before release."
icon: wand-magic-sparkles
---

# Build an app

An app packages everything that makes a capability work: the objects, the fields, the layouts, the views, the automation hooks, the workflows, and the permissions. Packaging matters because it is what makes the thing releasable and reversible.

{% stepper %}
{% step %}
## Write down the job it does

Before building anything, write one sentence describing what a user will do with the app and what they do today instead. If you cannot write it, the app is not ready to build.
{% endstep %}

{% step %}
## Create the app and add the objects

In **App Studio**, create the app and add the custom objects it needs. Define relationships to standard objects now rather than later. See [Custom objects](../data-model/custom-objects.md).
{% endstep %}

{% step %}
## Add fields and set the lifecycle

Add the fields and define the statuses records move through. Keep both lists short for the first release. See [Custom fields](../data-model/custom-fields.md).
{% endstep %}

{% step %}
## Build the layouts

Build a layout for each audience: the person creating records, the person reviewing them, and the read-only viewer. Put the fields each audience needs on their layout and nothing else.
{% endstep %}

{% step %}
## Add the views

Create the list views users will work from: my open records, records needing attention, records by owner. These are what people open daily, so name them for the task.
{% endstep %}

{% step %}
## Attach automation

Add the hooks that derive values, validate input, notify people, and create related records. Give each one an owner. See [Automation hooks](../automation/automation-hooks.md).
{% endstep %}

{% step %}
## Attach workflows

If records need approval, build the workflow against the object and test it in the simulator. See the [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).
{% endstep %}

{% step %}
## Set permissions

Configure who can create, read, and edit, and set field-level permissions where the data is sensitive. Start narrow.
{% endstep %}

{% step %}
## Test in the sandbox

Install the app in your sandbox environment and run every path with a real user from the intended audience watching. Watch where they hesitate.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Build the first version smaller than you think it needs to be. Fields, statuses, and automations are easy to add after release and difficult to remove, because views, conditions, and integrations start depending on them immediately.
{% endhint %}

## Design guidance

**Match the platform's conventions.** Users learn one set of habits from Zip's standard objects. An app that names, orders, and behaves like them needs almost no training.

**Do not rebuild what exists.** If your app needs an approval, use the workflow engine. If it needs reporting, use saved views. Reimplementing either inside an app means losing the audit trail and the permission model.

**Separate the record from the request.** A common mistake is modelling an app object that duplicates a purchase request. Relate to the request instead, so the spend stays in one place and reports correctly in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).

When the app works in the sandbox, release it following [Publish an app internally](publish-an-app.md).
