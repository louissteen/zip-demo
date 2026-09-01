---
description: "What Zip's AI features can see, what is excluded from model context, and how permissions and residency are enforced."
icon: lock-keyhole
---

# Data boundaries

A data boundary decides what reaches a model. Zip enforces boundaries at retrieval time, before context is assembled, rather than filtering an answer afterward.

## The permission boundary

Every AI feature runs as an identity: a person for [AI Procurement Concierge](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/), a service role for [Superagents](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/). Retrieval applies that identity's permissions to every record considered. A record the identity cannot open is never retrieved, never summarized, and never cited.

This means an AI feature cannot become a path around your access model. It also means fixing an over-broad answer usually starts with the underlying permission, not with the AI configuration.

## Field-level exclusions

Some fields are excluded from model context regardless of who is asking.

* Vendor bank account and payment instruction details
* Tax identification numbers on vendor records
* Credentials, keys, and tokens held on integrations
* Fields your administrator has marked sensitive on any object, including custom fields created in [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/)

Excluded fields are removed before context assembly. An AI feature can confirm that a field is present and complete without reading its value, which is enough for the completeness checks in [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

{% hint style="danger" %}
Banking details are excluded from model context and cannot be changed by an agent. Both controls are enforced at the platform level and are not configurable, because these are the fields payment fraud targets.
{% endhint %}

## Document boundaries

Contracts, invoices, and assessment documents are processed within the same boundary as the records they belong to. A document attached to a record the identity cannot see is not reachable.

## Residency and retention

Processing follows your tenant's configured region. Where your policy requires it, AI processing can be restricted to a region and features that would require processing outside it are disabled rather than silently rerouted.

Your content is not used to train shared models. Retention of AI activity records follows your tenant's retention configuration and is covered in [Compliance evidence](../assurance/compliance-evidence.md).

<details>
<summary>Mark a field as sensitive</summary>

Go to **Settings**, then **AI**, then **Governance**, and open the **Data boundaries** tab. Select the object, then mark the fields to exclude. Exclusions apply immediately to new retrieval. Existing conversations and open agent runs continue with the context they already assembled, so review open runs after a change that matters.

</details>

## Checking a boundary

Every run record and every Concierge answer lists what was retrieved and what was withheld, with the reason. Use those records to verify a boundary is doing what you configured rather than assuming it from the settings page. See [Agent runs](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/).
