---
description: "The field types available on an intake form, what each one produces, and which ones downstream logic can read."
icon: input-text
---

# Field types

Field type determines three things: what the requester sees, what the stored answer looks like, and whether workflows and routing rules can branch on it. The third is the one people forget.

## Free-form input

**Short text** collects a single line, such as a vendor contact name. Use it when there is no fixed set of answers.

**Long text** collects a paragraph. Use it for business justification and descriptions. Long text is not a good branching input, so do not build routing on it.

**Number** collects a numeric value with no formatting assumptions. Use it for quantities and headcount, not for money.

**Currency** collects an amount with a currency code, defaulted from the subsidiary. Always use currency rather than number for amounts, so thresholds compare correctly across entities.

**Date** collects a single date. Common uses are the required-by date and the desired contract start date.

## Choice fields

**Single select** presents a fixed list and stores one value. This is the workhorse for branching.

**Multi select** stores several values from a list. Useful for data types handled or regions affected.

**Yes or no** is a single select with two options. Prefer it over a checkbox when the answer drives routing, because an unchecked box and an unanswered question look the same.

**Checkbox** records an acknowledgement, such as confirming a policy has been read.

## Lookup fields

Lookups pull from records Zip already holds, so the answer is a real object rather than typed text.

**Vendor** searches existing vendor records and lets the requester propose a new vendor if none matches. A proposed vendor starts onboarding in [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

**User** searches your directory. Use it for the business owner or the technical contact.

**Department**, **subsidiary**, and **GL code** pull from synced master data and validate the answer against the ERP.

**Category** sets the taxonomy value for the request. See [Categories and subcategories](../taxonomy/categories-and-subcategories.md).

## Structured and supporting fields

**Line items** collect one or more rows with a description, quantity, unit price, and accounting dimensions. Use line items whenever a request may need to split across departments or GL codes.

**File upload** attaches documents. Accepts multiple files and is the right place for order forms and questionnaires.

**Section header** and **descriptive text** add structure and guidance without collecting an answer.

{% hint style="warning" %}
Changing a published field's type is disruptive. Existing requests keep their stored answers, but reports and rules that referenced the old type may stop matching. Add a new field and retire the old one instead.
{% endhint %}

## Choosing for branchability

If a workflow, routing rule, or budget check needs to read a field, it must be a select, yes or no, currency, number, date, or lookup. Text answers are for humans to read.

<details>

<summary>Example: choosing between text and select</summary>

Asking `Which country will this data be stored in?` as short text produces `US`, `usa`, `United States`, and `us-east-1` in the same column. Nothing can branch on that.

The same question as a single select with a fixed country list gives privacy reviewers a clean filter and lets a workflow add an EU data protection step automatically.

</details>
