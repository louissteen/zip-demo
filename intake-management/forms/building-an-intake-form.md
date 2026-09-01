---
description: "Create an intake form, organize it into sections, and preview it as a requester before you publish."
icon: pen-ruler
---

# Building an intake form

An intake form is a set of questions attached to one or more categories. Most organizations run a small number of forms, not one per purchase type, and use conditional logic to handle the variation.

## Build the form

{% stepper %}
{% step %}
## Create the form

Go to **Intake** and select **New form**. Give it a name a requester would recognize, such as `Buy something new`, rather than an internal name like `PR-Form-v3`.
{% endstep %}

{% step %}
## Add the identifying questions

Start with the questions that determine everything else: what you are buying, roughly how much it will cost, and which subsidiary and department it is for. These drive routing, so they belong near the top.
{% endstep %}

{% step %}
## Group the rest into sections

Add sections for vendor details, contract details, security details, and anything else your reviewers need. Sections are collapsible for the requester and make long forms feel shorter.
{% endstep %}

{% step %}
## Set required fields deliberately

Mark a field required only if a request cannot be routed or approved without it. Every extra required field is a reason someone abandons the form and buys on a credit card instead.
{% endstep %}

{% step %}
## Add conditional logic

Hide the sections that only apply to some requests. A software purchase needs the security questions; a catering order does not. See [Conditional logic](conditional-logic.md).
{% endstep %}

{% step %}
## Preview as a requester

Use **Preview** to walk the form as an employee would. Check that the visible path for each common scenario is short and that nothing you hid is still required.
{% endstep %}
{% endstepper %}

## Structuring questions for reviewers

Reviewers do not want to hunt. Group questions by the team that reads them, and name the section after the outcome rather than the team: **Security and data handling** reads better than **InfoSec questionnaire**.

Where a reviewer needs a document rather than an answer, use a file upload field and say what you expect: an order form, a data processing addendum, a completed security questionnaire.

{% hint style="info" %}
Ask the requester only for what the requester knows. Anything procurement, finance, or AP can determine later, including GL codes, tax treatment, and payment terms, should be captured downstream rather than on the intake form.
{% endhint %}

## Keeping forms short

Two techniques do most of the work:

**Pre-fill from the requester's profile.** Subsidiary, department, and manager can be derived from the user record rather than asked.

**Branch on amount.** A low-value request can skip the questions that only matter above a threshold. Set the threshold with your finance team so it matches the policy in [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/).

When the form is ready, publish it following [Form versioning](../publishing/form-versioning.md), then confirm it routes correctly using [Routing rules](../publishing/routing-rules.md).
