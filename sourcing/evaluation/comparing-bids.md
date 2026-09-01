---
description: "Read supplier responses side by side and normalize pricing so the comparison is fair."
icon: table-columns
---

# Compare bids

Once an event closes and responses are unsealed, the comparison view puts every supplier's answers in a single grid. Questions run down the page, suppliers run across it, and you read one row at a time instead of opening six documents.

## The comparison grid

Each row is a question, a requirement, or a pricing line. Each column is a supplier. You can hide suppliers to focus on a shortlist, collapse sections you have finished, and pin a supplier column so it stays visible as you scroll.

Requirement rows show met, not met, or partially met, so a supplier failing a mandatory requirement is visible immediately rather than buried in narrative.

## Normalizing pricing

Bids are rarely comparable as submitted. Zip normalizes on three axes.

**Currency.** Prices quoted in different currencies are converted at a single rate as of a date you set, so exchange movement during the event does not decide the award.

**Term.** A three-year price and a one-year price are shown on a common annualized basis, and total cost across the full term is calculated for each.

**Structure.** Suppliers that bundle differently are compared on the fixed line items you defined in the pricing sheet. Anything a supplier added outside the sheet appears in a separate section rather than being silently folded into the total.

{% hint style="warning" %}
Normalization makes numbers comparable, not equivalent. A supplier quoting a lower annual price on a five-year lock is not offering the same thing as one quoting a higher price on an annual term. Note the difference in the evaluation rather than letting the normalized total decide.
{% endhint %}

## AI summarization

Long narrative answers can be summarized so evaluators reading a section see the substance of each response and the differences between them before reading in full. Summaries are labeled as generated and always sit alongside the supplier's original text, which is what evaluators score. For how AI features are governed and what data they use, see [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

## Working with evaluators

Evaluators are assigned to sections. A security reviewer sees the security section, a finance reviewer sees pricing. Section assignment does two things: it keeps evaluators from scoring outside their competence, and it stops a technical evaluator from being anchored by a price they should not be weighing.

Evaluators leave comments on individual answers. Comments are visible to the event owner and to other evaluators on the same section, and they stay with the event as part of the award record.

## Clarification rounds

If a response is ambiguous, send a clarification request to that supplier. The supplier answers in the portal and the answer is attached to the original response rather than replacing it, so the change is visible.

If several suppliers need to revise, issue a further round instead. The event returns to open for the shortlisted suppliers with a new deadline, and both rounds are retained for comparison.

## Exporting

The comparison grid exports to a spreadsheet for offline review or for a committee that does not have Zip access. The export carries the same normalized figures shown on screen.
