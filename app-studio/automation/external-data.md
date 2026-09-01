---
description: "Show data from other systems on a Zip record, and decide when to fetch it live rather than copy it in."
icon: plug
---

# Embedding external data

Approvers make better decisions with context that lives elsewhere: the ticket, the asset record, the usage figures, the credit check. App Studio lets you bring that context onto the Zip record without copying whole systems into it.

## Fetch or store

The first decision is whether the data lives in Zip or is fetched when needed.

**Fetch live** when the value changes often, when it is only needed while someone is looking at the record, and when the source system is reliable. Live values are always current and nothing has to be kept in sync.

**Store a copy** when the value must be reportable, filterable, or usable in a workflow condition, or when it must be preserved as it was at decision time. A stored copy is the only option if an approver's decision depends on it and you need to show later what they saw.

Many implementations do both: store the handful of fields that drive decisions, and fetch the rest for display.

{% hint style="info" %}
Anything a workflow branches on should be stored, not fetched. A condition that depends on a live call fails whenever the other system is unavailable, and an approval chain that cannot be built is a worse outcome than a slightly stale value.
{% endhint %}

## Connections

External calls run through a connection configured once by an administrator. A connection holds the base URL, the authentication method, and the credentials, which are stored encrypted and never exposed to the app definition or to logs.

Configure a separate connection per environment so a test app cannot write to a production system.

## Displaying external data

Two presentation options:

**Embedded panel.** A section on the record layout that renders fetched data as a set of labelled values or a small table. Use for reference context an approver reads.

**Derived fields.** Stored fields populated by an automation hook from an external call. These behave like any other field: filterable, reportable, and readable by workflows. See [Automation hooks](automation-hooks.md).

## Failure behavior

External systems fail. Decide in advance what the record does when they do.

**For a display panel**, show a clear unavailable state with the last successful fetch time. Do not show a blank panel, which reads as "there is nothing here".

**For a derived field**, keep the last known value and record the failure. Overwriting a good value with an empty one because a call timed out is the most damaging thing an integration can do quietly.

**For anything gating a decision**, surface the failure to the approver rather than hiding it. An approver should know they are looking at stale context.

## Direction of travel

Embedding brings data in. For pushing Zip data out, use the [API](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/) and webhooks rather than an app hook, so the other system controls its own retry and backfill.

For the standard integrations Zip ships with, including ERP master data and contract systems, use the packaged integration rather than building a connection. Custom connections are for systems Zip does not integrate with, not for replacing ones it does.

## Reviewing what is connected

Keep a register of the connections in use, what they read, and who owns them. Review it when a source system is retired or migrated, because an app quietly reading from a decommissioned endpoint fails at the least convenient moment.
