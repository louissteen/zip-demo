---
description: "Model a record type Zip does not ship, relate it to standard objects, and give it its own lifecycle and permissions."
icon: table
---

# Custom objects

A custom object is a record type you define. It has fields, a lifecycle, relationships to standard objects, and its own permissions. Use one when the thing you need to track has a life of its own, separate from any single request.

## When a custom object is the right answer

Ask whether the thing has its own lifecycle and its own history. If it does, it is an object. If it is a property of something else, it is a field.

**Good candidates**: a software license entitlement tracked across renewals, an internal cost recovery agreement, a hardware asset assigned to an employee, a data processing record maintained per vendor, an internal project that several requests charge to.

**Poor candidates**: a business justification, a preferred delivery date, a cost center override. These are fields on a request.

{% hint style="info" %}
Before building an object, check whether a standard one already fits. Vendor records, contracts, and requests each carry more behavior than a custom object will, and reusing them keeps your reporting joined up.
{% endhint %}

## Defining an object

An object definition has four parts.

**Identity.** A name, a plural name, and a record label pattern that determines how records are titled in lists.

**Fields.** The attributes of the record. See [Custom fields](custom-fields.md).

**Relationships.** Links to standard objects and to other custom objects. A relationship is either a lookup, where the record points at one other record, or a collection, where it points at many.

**Lifecycle.** The set of statuses a record moves through, and which transitions are allowed. Keep the list short. Five statuses is usually enough, and every extra one is a state somebody has to interpret.

## Relating to standard objects

Relationships are what make a custom object useful rather than a parallel spreadsheet.

A `Project` object related to purchase requests lets a requester pick a project on the intake form, lets a workflow branch on the project owner, and lets spend be reported by project without a new dimension in the ERP.

A `License entitlement` object related to a vendor record and to contracts lets a renewal request show what is currently owned before anyone negotiates.

## Permissions

Custom objects carry their own permission configuration, using the same roles and scopes as the rest of Zip. Decide three things:

- Who can create records.
- Who can read them, and whether the scope is by subsidiary, department, or ownership.
- Who can edit which fields, and in which statuses.

The default should be narrow. Widening access later is easy; discovering that everyone could read a sensitive object is not. See [Roles and permissions](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/).

## Where custom objects appear

Once published, an object behaves like a native one:

- Records appear in list views, and views over them can be saved and shared.
- Fields are available in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/) as columns and filters.
- Workflows can be triggered by record creation and change, and can branch on the object's fields. See the [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).
- Every change is written to the audit log.
- Records are readable and writable through the [API](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).

## Changing an object after release

Adding fields and statuses is safe. Removing them is not: existing records keep the data, but views, workflow conditions, and integrations referencing the removed element stop matching. Deprecate first, watch for a period, then remove.
