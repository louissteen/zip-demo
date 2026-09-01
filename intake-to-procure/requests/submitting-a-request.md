---
description: "Raise a purchase request in Zip and answer the intake questions that route it."
icon: pen-to-square
---

# Submit a purchase request

A purchase request (PR) is how you tell Zip you want to buy something. You do not need to know which team has to approve it, which category it falls under, or whether the vendor is already onboarded. Zip works that out from your answers.

{% stepper %}
{% step %}
## Open a new request

From the Zip home page, select **New request**. If your organization has published more than one intake form, pick the one that matches what you are doing, for example a new purchase, a renewal, or a change to an existing contract.
{% endstep %}

{% step %}
## Describe what you need

Enter a short title and a description of the purchase. Write the description for someone outside your team: what the product or service does, why you need it, and what happens if you do not get it. Approvers read this first.
{% endstep %}

{% step %}
## Select the vendor

Search for the vendor by name. If the vendor already exists in Zip, select it and continue. If it does not, select **Add new vendor** and enter the vendor name and a contact email. Zip starts [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/) for that vendor in parallel with your request.
{% endstep %}

{% step %}
## Enter amount and accounting details

Enter the estimated amount, currency, and the period the spend covers. Depending on how your intake form is configured, you may also select a department, cost center, GL code, category, and subcategory. Many of these default from your user profile.
{% endstep %}

{% step %}
## Attach supporting documents

Upload the quote, order form, statement of work, or draft contract. Zip reads uploaded documents and can prefill fields such as amount, term dates, and vendor name for you to confirm.
{% endstep %}

{% step %}
## Review and submit

Zip shows the approval chain your answers produced before you commit. Check it, then select **Submit**. The request moves to **In review** and the first approver is notified.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
You can save a request as a draft at any point and come back to it. Drafts are visible only to you and are not routed to anyone.
{% endhint %}

## After you submit

Zip notifies approvers by email and, if your organization has the integration enabled, in Slack or Microsoft Teams. Approvers can act without leaving the notification.

If an approver needs something from you, they can send the request back with a comment. It returns to you as **Needs info**, you edit the affected fields, and it resumes from the step where it stopped rather than starting over.

<details>

<summary>What if I am not sure of the final amount?</summary>

Enter your best estimate and say so in the description. The estimate determines which approval thresholds apply, so a low guess that later turns out to be wrong can send the request back for re-approval. If the final number lands in a higher threshold band, Zip re-runs routing and adds the approvers the new amount requires.

</details>

<details>

<summary>Can someone else submit on my behalf?</summary>

Yes. A requester can set a different person as the requester of record, for example an executive assistant raising a request for a leader. Notifications go to both people.

</details>
