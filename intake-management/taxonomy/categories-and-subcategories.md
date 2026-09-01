---
description: "The taxonomy that organizes what people can request, and the single most important input to routing and reporting."
icon: folder-tree
---

# Categories and subcategories

A category answers the question "what is this?" in a way that both a requester and a workflow can use. It is not the GL code, and it is not the vendor. It is the type of thing being bought.

Categories are two levels: a category such as `Software`, and a subcategory such as `Security software` or `Design tools`. The pair drives routing, reporting, and often the reviews required.

## Why the taxonomy matters

Three systems read the category:

**Routing.** The workflow engine branches on category more than on anything else. `Professional services` goes to legal; `Hardware` goes to IT asset management; `Marketing` goes to brand review.

**Reporting.** Spend by category is the view finance actually asks for. GL code answers where the money posted, category answers what it bought. See [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).

**Requester guidance.** The category picker is the requester's first decision. If they can find their purchase in it quickly, the rest of the form goes well.

## Designing the taxonomy

Start narrow. A first-year taxonomy of twelve to twenty categories, each with a handful of subcategories, covers most organizations. It is much easier to split a category later than to merge two that people have been using inconsistently.

**Name for the requester, not the accountant.** `Contractors and staffing` finds more correct submissions than `Outside services, non-capitalized`.

**One home per purchase.** If a purchase plausibly belongs in two categories, the names are wrong. Rename until the boundary is obvious.

**Do not encode amount or urgency.** Those are separate fields. A category called `Large software purchase` breaks reporting and duplicates a threshold you can express in a condition.

{% hint style="info" %}
Map each category to a default GL code where your chart of accounts supports it. Requesters pick a category they understand, and the accounting dimension is derived, which removes the most common source of miscoded requests.
{% endhint %}

## Attaching behavior to a category

Categories carry configuration, so most policy can be expressed once rather than repeated in every workflow:

- The intake form used when that category is selected.
- Default GL code, and in some cases default department.
- Required reviews, such as a security review for all software.
- Required documents, such as a statement of work for services.
- The procurement owner responsible for that spend area.

## Maintaining the taxonomy

<details>

<summary>Adding a category</summary>

Confirm the purchase does not already fit an existing category, agree the default GL mapping with finance, decide which reviews it triggers, then add it and publish. New categories take effect for new requests only.

</details>

<details>

<summary>Retiring a category</summary>

Deactivate rather than delete. A deactivated category stops appearing in the picker but still renders on historical requests and in reports, so prior-year comparisons stay intact.

Before deactivating, check whether any workflow or routing rule branches on it. A rule pointing at a retired category silently stops matching.

</details>

<details>

<summary>Splitting a category</summary>

Create the new subcategories alongside the existing one, redirect routing to them, then deactivate the original. Do not rename in place: renaming changes what historical records appear to say.

</details>
