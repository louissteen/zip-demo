---
description: "Add fields to standard and custom objects, control who can see and edit them, and keep them usable for reporting and workflows."
icon: list-check
---

# Custom fields

Custom fields extend an object with attributes your organization needs. They can be added to standard objects such as requests, purchase orders, vendors, and bills, and to any custom object you define.

## Field types

The types available mirror those on intake forms: short text, long text, number, currency, date, single select, multi select, yes or no, checkbox, file attachment, and lookups to users, vendors, departments, GL codes, and custom objects.

Choose the type for how the field will be used, not how it will be typed. If a workflow, a filter, or a report needs to read it, it must be a select, a number, a currency, a date, a yes or no, or a lookup. Free text cannot be branched on reliably. See [Field types](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/) for the longer argument.

## Where a field appears

A custom field is defined once and surfaced deliberately. For each field, decide:

**Which layouts show it.** A field on the vendor record does not have to appear on every vendor view.

**Whether it is exposed on intake.** Fields on the request object can be added to intake forms, where requesters answer them, or kept internal, where only operators see them.

**Whether it is visible to approvers.** Approvers see a subset of the record. A field that reviewers need must be on the layout they see, or it may as well not exist.

## Value sources

Select fields can take options from three places.

**A static list**, maintained in the field definition. Right for short, stable lists.

**A synced list**, from master data such as departments or GL codes. Right when the ERP owns the values.

**A derived value**, calculated from other fields by an automation. Right for things like a risk tier computed from several answers. See [Automation hooks](../automation/automation-hooks.md).

{% hint style="warning" %}
Editing the option list of a live select field affects existing records. Removing an option leaves records holding a value that is no longer selectable and no longer matches filters looking for the current list. Deactivate options rather than deleting them.
{% endhint %}

## Required, default, and validation

**Required** should be set on the layout, not globally, so a field can be mandatory for the team that owns it without blocking everyone else.

**Defaults** reduce work. Defaulting a field from the requester's profile or from the selected category is almost always better than asking.

**Validation** restricts what can be entered: a numeric range, a date that must be in the future, a text pattern. Validation messages should say what is expected, not that the value is invalid.

## Field-level permissions

Fields can be readable by one set of users and editable by another. Common uses are a negotiated price visible to procurement but not the requester, and a risk classification editable only by the security team.

Field-level permissions are enforced everywhere, including in views, exports, and the API.

## Keeping the field list manageable

Custom fields accumulate. Every one adds a column to consider, a filter to maintain, and a question somebody has to answer.

Review the list annually. For each field, check whether it has been populated on recent records and whether anything reads it. A field nobody fills in and nothing reads should be retired, following the deprecate-then-remove sequence in [Custom objects](custom-objects.md).
