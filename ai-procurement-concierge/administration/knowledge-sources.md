---
description: "The policy, catalog, and record context AI Procurement Concierge is allowed to read, and how administrators connect and scope each source."
icon: books
---

# Knowledge sources

The Concierge answers only from sources an administrator has connected. There is no general knowledge fallback for policy questions, which is why an unconnected topic produces a handoff rather than an invented answer.

## Source types

**Procurement policy.** Documents you upload or link, plus the policy text held on categories and subcategories in Zip. This is the primary source for "am I allowed to" questions.

**Workflow conditions.** The routing conditions configured in the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/). Reading conditions directly means the Concierge describes the approval path that will actually run, not a written summary of it that has drifted.

**Vendor and contract records.** Vendor records, contract terms extracted by [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/), and renewal dates. This is what lets the Concierge say "we already have this".

**Catalog and preferred vendors.** Approved vendors by category, with any preferred-vendor guidance attached.

**Request objects.** Purchase requests, purchase orders, invoices, and bills, used for status answers. See [Intake-to-Procure](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/) and [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).

**Help content.** Your internal procurement help articles, for process questions your policy does not cover directly.

## Connect a source

{% stepper %}
{% step %}

## Open Concierge settings

Go to **Settings**, then **AI**, then **Concierge**, and open the **Knowledge** tab.

{% endstep %}
{% step %}

## Add the source

Select **Add source** and choose the source type. Document sources accept an upload or a link to a synced location. Record sources are enabled rather than uploaded, because the data already lives in Zip.

{% endstep %}
{% step %}

## Scope the audience

Set which departments, subsidiaries, or regions the source applies to. A regional policy scoped to one subsidiary is never used to answer a requester in another.

{% endstep %}
{% step %}

## Set the owner and review date

Name the team that owns the source and the date it should next be reviewed. Sources past their review date are flagged in coverage reporting.

{% endstep %}
{% step %}

## Publish

Select **Publish**. New answers use the source immediately. Existing conversations are unaffected.

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Connecting a source does not widen who can see its contents. The Concierge checks the requester's permissions on every record it retrieves before it composes an answer, and it omits anything they could not open themselves. See [data boundaries](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).
{% endhint %}

## Keeping sources current

Retire a source when it is superseded rather than leaving two versions connected. Conflicting sources are the most common cause of an answer that is defensible in isolation but wrong in context. When two connected sources disagree, the Concierge reports the conflict and hands off rather than picking one.
