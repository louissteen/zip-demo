---
description: "Attach budgets to departments, categories, GL codes, and cost centers so requests find the right one automatically."
icon: link
---

# Mapping budgets to your org

Mapping is how Zip works out which budget a line item consumes. Get this right and requesters never think about budgets at all; get it wrong and either nothing is tracked or everything hits the wrong budget.

## The mapping dimensions

A budget can be mapped on any combination of:

- **Subsidiary**, always required, and always a single value.
- **Department** or **cost center**, one or many.
- **Category** or **subcategory**, one or many.
- **GL code**, one or many.

A line item matches a budget when it satisfies every mapped dimension. Dimensions you leave unmapped are treated as unrestricted.

## How specific to be

The trade-off is coverage against precision.

**Broad mapping**, for example department only, catches everything that department spends. Nothing falls through, but the budget tells you little about what the money went on.

**Narrow mapping**, for example department plus three GL codes, gives a precise picture but leaves everything else uncovered.

A practical pattern is a two-tier structure: narrow budgets for the spend areas a team actively manages, plus one broader departmental budget that catches the remainder.

{% hint style="info" %}
Report on unmapped spend regularly. Approved requests that matched no budget are the blind spot in every budget deployment, and the number is usually larger than people expect in the first quarter.
{% endhint %}

## Resolving overlaps

A line item can match more than one budget. Zip resolves the conflict by specificity: the budget matching on the most dimensions wins.

<details>

<summary>Worked example</summary>

Two budgets exist for the US subsidiary:

- **Budget A**: department `Engineering`. Mapped on one dimension.
- **Budget B**: department `Engineering`, category `Software`, GL code `6120`. Mapped on three.

An engineering request for a software tool coded to `6120` matches both. Budget B is more specific, so it consumes Budget B.

An engineering request for conference travel matches Budget A only, and consumes it.

</details>

Where two budgets are equally specific, the request is flagged as ambiguous and the budget owner is asked to resolve it. Ambiguity is a configuration error rather than a runtime one, so fix the mapping instead of resolving each case by hand.

## Splitting across budgets

Mapping is evaluated per line item, not per request. A request with two lines charged to different departments consumes two budgets, each for its own line amount.

This is the reason to use line items rather than a single header amount on your intake forms. See [Field types](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).

## Keeping mappings current

Department reorganizations break mappings quietly. A department that is merged into another leaves its budget mapped to a dimension nothing codes to any more, and the budget then shows perfect adherence because nothing is consuming it.

Review mappings whenever master data changes, and check for budgets with zero consumption partway through a period. Zero consumption is occasionally good news and usually a broken mapping.

Once mapped, decide how strictly the budget is enforced in [Soft and hard limits](../controls/soft-and-hard-limits.md).
