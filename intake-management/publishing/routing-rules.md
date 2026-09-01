---
description: "Send each submitted request to the right form, the right workflow, and the right procurement owner."
icon: route
---

# Routing rules

Routing happens twice: once before the form, deciding which form a requester sees, and once after submission, deciding which workflow the request runs and who owns it.

## Routing to a form

When a requester starts a request, Zip picks the form based on what they have told it so far. In most configurations the requester selects a category or an entry point on the landing page, and that selection determines the form.

Keep entry-point routing simple. If the requester has to understand your internal org chart to choose an entry point, the routing is doing work the form should do with a category question.

## Routing after submission

Once submitted, the request is evaluated against your routing rules. A rule has conditions and an outcome.

**Conditions** read the submitted answers: category, subcategory, amount, subsidiary, department, vendor, and any branchable custom field.

**Outcomes** set one or more of:

- The workflow the request runs.
- The procurement owner assigned to shepherd it.
- The queue or team the request appears in.
- Any required review flagged at submission, such as security or privacy.

## Rule order and matching

Rules are evaluated in order, top to bottom. The first match wins unless a rule is marked as continuing evaluation.

Order rules from most specific to most general, and always end with a catch-all that assigns a default workflow and owner. A request that matches no rule is an unrouted request, and unrouted requests are what people complain about.

{% hint style="warning" %}
Test the catch-all deliberately. Submit a request with an unusual combination of answers and confirm it lands somewhere a human monitors, rather than in a queue nobody opens.
{% endhint %}

## Worked example

<details>

<summary>A three-rule set for a mid-size company</summary>

**Rule 1.** Category is `Software` AND data types handled contains `Customer PII`. Outcome: run the software workflow, flag privacy review, assign the IT procurement owner.

**Rule 2.** Category is `Professional services` AND amount is greater than the services threshold. Outcome: run the services workflow, require a statement of work, assign the services procurement owner.

**Rule 3.** Catch-all, no conditions. Outcome: run the standard workflow, assign the procurement inbox.

A request for a design agency under the threshold falls through rules 1 and 2 and lands on rule 3, which is correct: it still gets an owner and an approval chain.

</details>

## Reassignment after routing

Routing sets a starting point, not a permanent one. A procurement operator can reassign the owner, and a workflow can add steps that routing did not anticipate. Both actions are recorded on the request history.

If you find operators reassigning the same kind of request repeatedly, that is a routing rule waiting to be written.

## Where routing ends and workflow begins

Routing decides *which* workflow runs. The workflow decides *who* approves and in what order. Keep the split clean: putting approver selection into routing rules duplicates logic that the [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/) already expresses, and makes both harder to change.
