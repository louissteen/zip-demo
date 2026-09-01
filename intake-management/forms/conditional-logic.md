---
description: "Show and hide questions based on earlier answers so requesters only see what applies to their purchase."
icon: code-branch
---

# Conditional logic

Conditional logic is what lets one form serve every kind of purchase. Instead of building separate forms for software, services, hardware, and marketing spend, you build one form where most questions are hidden most of the time.

## How conditions are evaluated

Every field and section can carry a visibility condition built from earlier answers. Conditions evaluate as the requester types, so the form reshapes itself immediately.

Two rules govern behavior:

**A condition can only reference a field that appears earlier in the form.** Forward references are rejected when you save, because the answer would not exist yet.

**A hidden field is not answered.** If a field is hidden, its value is cleared and its required setting does not apply. This is why you can safely mark conditional fields required.

## Building a condition

A condition is one or more clauses joined by AND or OR. Each clause compares a field to a value:

- Category **is** `Software`
- Estimated annual spend **is greater than** `50,000`
- Data types handled **contains** `Customer PII`
- Contract required **is** `Yes`

Group clauses when the logic is not a flat list. Showing the security section for software purchases above a threshold, or for any purchase that touches customer data, is two groups joined by OR.

{% hint style="info" %}
Write conditions against stable fields. Basing logic on a free-text field, or on a select whose options change often, produces forms that quietly stop branching when someone edits the option list.
{% endhint %}

## Patterns that work

**Progressive disclosure by category.** Ask the category first, then reveal the section that belongs to it. This is the single highest-value use of conditional logic.

**Threshold-driven detail.** Below a spend threshold, ask for a description and a vendor. Above it, ask for the competitive alternatives considered and a business case.

**Vendor-aware questions.** If the selected vendor already has a completed security review, hide the security section. The requester never sees questions your organization has already answered.

**Escape hatches.** Add an `Other` option to selects, with a follow-up text field revealed by it, so unusual purchases do not stall at the form.

## Anti-patterns

**Deep chains.** Conditions that depend on fields that are themselves conditional become impossible to reason about. Keep chains to two levels.

**Hiding required accounting fields.** If a GL code is required for routing and you hide it, the request submits without one and stalls downstream. Derive it instead of hiding it.

**Using logic to enforce policy.** Conditional logic controls what is asked, not what is allowed. Enforcement belongs in the [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/) and in [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/), where the decision is recorded and auditable.

## Testing your logic

Preview the form and walk each branch you expect requesters to take. For each one, confirm the visible path is short, the right sections appear, and nothing hidden blocks submission.

Then check the reverse: change an answer that hides a section you already filled in, and confirm the cleared values do not reappear if you switch back. Cleared is cleared, by design.
