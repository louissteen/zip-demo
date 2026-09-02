---
description: Design the questions requesters answer and the data those answers produce.
---

# Build intake forms

An intake form is the set of questions a requester answers. It has two jobs: collect what approvers need to make a decision, and produce the structured data that routing conditions read. A form that asks a lot but produces nothing structured makes routing impossible, so build the two together.

Intake forms are configured by administrators on the **Intake** settings page.

## Question types

Zip supports short text, long text, number, currency amount, date, single select, multi select, user picker, vendor picker, and file upload. Select and picker questions are the ones routing conditions can test, so use them for anything that decides who approves.

Fields can be marked required, hidden, or read only, and any of those states can itself be conditional.

## Conditional questions

Questions can appear only when an earlier answer calls for them. A question asking whether the vendor will process customer data appears only when the request is for software. A question asking for a data processing agreement appears only when the answer to that question is yes.

Keep the first screen short. Conditional depth is cheaper than a long flat form, because most requesters never see most of the questions.

{% hint style="info" %}
Every question you add is a question every requester reads. Before adding one, decide which approver needs the answer and what they would do differently without it. If nobody would act differently, do not ask it.
{% endhint %}

## Prefill and AI assistance

Several kinds of data can populate without the requester typing it.

**Profile defaults.** Department, cost center, subsidiary, and manager come from the requester's user record.

**Document extraction.** When a requester uploads a quote or order form, Zip reads it and proposes values for amount, currency, term start and end, and vendor. The requester confirms or corrects them.

**Vendor lookup.** Selecting an existing vendor pulls in its category, risk tier, onboarding state, and existing contracts, which routing can then read without asking the requester anything.

## Publishing and versioning

Forms are versioned. Editing a published form creates a new version, and requests already in flight continue on the version they were submitted under. This matters for audit: the form a request was answered against is preserved with the request.

Use the preview to walk the form as a requester before publishing, including the conditional branches.

{% stepper %}
{% step %}
## Draft the form

Add your questions and set conditions on the ones that should not always appear.
{% endstep %}

{% step %}
## Test the branches

Use **Preview** and answer as a requester would. Walk each branch that leads to a different approval outcome.
{% endstep %}

{% step %}
## Check the routing it produces

Preview shows the approval chain your test answers generate. Confirm it matches your policy before anyone sees the form.
{% endstep %}

{% step %}
## Publish

Publish the version and assign it to the request types that should use it.
{% endstep %}
{% endstepper %}

For deeper configuration of form logic and reusable question sets, see [Intake Management](https://app.gitbook.com/o/6WfIzfI8ygNrqaIpvHah/s/klfPYPbO77zxOWiQGk7y/).
