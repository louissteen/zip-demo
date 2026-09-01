---
description: "How conditions are written, when they are evaluated, and what happens when a record changes mid-chain."
icon: filter
---

# Conditions and branching

A condition is a test against the record. If it passes, the step it gates is included in the chain. If it fails, the step is skipped and recorded as skipped.

## Writing a condition

A condition is one or more clauses joined by AND or OR, and clauses can be grouped. Each clause has a field, an operator, and a value.

Common fields to branch on:

| Field | Typical use |
| --- | --- |
| Category, subcategory | Which functional reviews apply |
| Total amount | Approval thresholds |
| Subsidiary | Entity-specific policy |
| Department, cost center | Departmental sign-off |
| Vendor risk tier | Extra diligence for higher-risk vendors |
| Contract required | Whether legal is involved |
| Budget check result | Whether finance approval is needed |
| Custom intake field | Anything specific to your policy |

Operators depend on the field type: equals and not equals for selects, greater than and less than for amounts and dates, contains and does not contain for multi-selects and lookups.

{% hint style="warning" %}
Amount comparisons happen in the subsidiary's currency. A threshold expressed in USD does not translate itself for a EUR subsidiary. Either define thresholds per subsidiary, or use a workflow condition on the converted amount field so every entity is compared consistently.
{% endhint %}

## When conditions evaluate

Conditions evaluate at two moments.

**When the chain is built**, on submission. This produces the initial set of steps.

**When the record materially changes**, such as an amount increase, a category change, a vendor change, or a new line item. The chain is recalculated.

## Recalculation rules

Recalculation is additive and does not undo history:

**Newly qualifying steps are inserted** at the correct position. If they sit before the current step, the chain returns to them.

**Steps that no longer qualify are skipped** if they have not yet been actioned.

**Completed approvals are preserved** unless the change invalidates the basis on which they were given. A material increase in amount re-triggers the approvals gated on amount thresholds; a typo fix in the description does not.

<details>

<summary>What counts as material</summary>

Material change is configurable per workflow. Most organizations treat these as material: an increase in total amount beyond a tolerance, a change of vendor, a change of category or subcategory, adding a line item, and changing the subsidiary.

Non-material by default: editing the description or justification, attaching a document, adding a comment, and changing the required-by date.

Set the tolerance with finance. A tolerance of zero means every rounding correction restarts approvals, which is how workflows acquire a reputation for being slow.

</details>

## Branching without duplicating workflows

The instinct when policy differs by entity or category is to build a separate workflow for each. Resist it. Duplicated workflows drift, and a policy change then has to be made in six places.

Prefer one workflow with conditional steps. Use the subsidiary field in conditions to express entity-specific policy, and the category field to express functional policy. Split into a separate workflow only when the shape of the process genuinely differs, for example a sourcing event handled through [Sourcing](https://app.gitbook.com/s/yWPKTXf10NGJgEVmE6Ok/) rather than a direct purchase.

## Debugging a condition

When a step fires unexpectedly, or fails to fire, open the record's chain and expand the step. Zip shows the condition as evaluated, including the field values it read. In most cases the answer is that a field was empty, and an empty field does not satisfy a `does not equal` clause the way people expect.

Test conditions against real records before publishing, using the simulator described in [Test and publish a workflow](../release/test-and-publish.md).
