---
description: "The question types AI Procurement Concierge handles, the context it uses to answer them, and the questions it refuses."
icon: circle-question
---

# What the Concierge answers

The Concierge is scoped to procurement. It answers from your configured policy, your catalog, your vendor records, and the requests the person asking is allowed to see. It does not answer general questions that have nothing to do with buying.

## Question types

**Policy questions.** "Do I need a security review for a tool that stores customer data?" "What is the approval path for a renewal over my department threshold?" The Concierge answers from your published procurement policy and from the conditions configured in the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/), so the answer reflects the rules that will actually run.

**Catalog and vendor questions.** "Do we already have a contract for this?" "Which of our approved vendors covers translation services?" The Concierge checks existing vendor records and contracts before a requester starts a duplicate purchase. This is the highest-value question type for most customers, because it prevents spend rather than routing it.

**Process questions.** "Which intake form do I use for a professional services engagement?" "What do I need before legal will look at this?" The Concierge names the form, lists the information the form will ask for, and can open it directly.

**Status questions.** "Where is my request?" "Who is holding this up?" The Concierge reads the request, its current approval step, and the assigned approver, then reports where the item is sitting and what the next step is.

## Questions it refuses

The Concierge declines rather than guesses when a question falls outside its scope or its permissions.

* Questions about records the person asking cannot see. The Concierge inherits the requester's permissions and never summarizes a record they lack access to.
* Legal advice, tax advice, or an interpretation of contract language that your policy has not already settled. It points to the relevant clause and routes to legal instead.
* Commitments on behalf of the company: negotiated pricing, delivery dates, or whether an exception will be granted.
* Questions with no configured source. If your policy is silent, the Concierge says so and offers a handoff rather than inferring a rule.

{% hint style="warning" %}
A confident answer to an unconfigured question is the failure mode that damages trust in the assistant. If requesters report answers that sound plausible but do not match your policy, check [Coverage reporting](../administration/coverage-reporting.md) for the topics with no source behind them.
{% endhint %}

<details>
<summary>How the Concierge decides between answering and deflecting</summary>

For each question, the Concierge retrieves candidate context from the sources an administrator has enabled, checks the requester's permissions against every record it retrieved, and evaluates whether the retrieved context actually answers the question. If nothing sufficient comes back, it deflects to a handoff rather than composing an answer from general knowledge. Administrators can raise or lower this threshold per topic in [Tuning answers](../administration/tuning-answers.md).

</details>
