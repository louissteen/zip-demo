---
description: "Start a new agreement, renewal, or amendment from intake."
icon: file-circle-plus
---

# Request a contract

Business users request contracts through the same intake they use to request a purchase. They do not need to know whether the situation calls for a new master agreement, an order form, or an amendment. The intake questions establish that, and Zip routes accordingly.

{% stepper %}
{% step %}
## Start the request

Select **New request** and choose the contract intake form. If you are already in a purchase request that needs paper, select **Request contract** on that request so the two records are linked.
{% endstep %}

{% step %}
## Say what kind of agreement you need

Choose new agreement, renewal, amendment, or termination. For a renewal or amendment, select the existing contract from the repository. Zip carries over the counterparty, the term, and the current commercial terms.
{% endstep %}

{% step %}
## Identify the counterparty

Select the vendor. If the counterparty is not in Zip, enter the legal entity name exactly as it should appear on the agreement, along with a contact for negotiation.
{% endstep %}

{% step %}
## Answer the risk-relevant questions

The form asks what the vendor will do: whether it processes personal data, connects to internal systems, holds regulated data, or performs work on site. These answers determine whether privacy, security, and other reviewers join the chain, and whether a risk assessment starts. See [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/).
{% endstep %}

{% step %}
## Enter the commercial terms

Value, currency, term length, start date, renewal type, and payment terms. If a sourcing event produced these, they are prefilled from the award.
{% endstep %}

{% step %}
## Attach the paper

Upload the supplier's agreement if they have sent one, or select your organization's template if you are papering the deal. Zip reads whichever document you provide and extracts the key terms for review.
{% endstep %}

{% step %}
## Submit

Zip shows the review chain your answers produced. Submit, and the first reviewer is notified.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Attach the actual document rather than a summary of it. Clause extraction, redline comparison, and obligation tracking all read the document. A request submitted with terms typed into a text field gets none of them.
{% endhint %}

## Papering on your template versus theirs

Where you have a choice, starting from your own template is faster, because your positions are already the ones your playbook expects. Zip generates a draft from your template populated with the commercial terms from the request.

Where the supplier insists on its paper, which is normal for large software vendors, upload theirs. The redline review compares it against your playbook rather than against your template, so the process is the same from legal's side.

<details>

<summary>What if I do not know which template to use?</summary>

Leave the template unselected and describe the arrangement in the request. The legal reviewer selects the right template as the first step of review. Most organizations find that a handful of common cases can be selected by the requester and the rest are better left to legal.

</details>
