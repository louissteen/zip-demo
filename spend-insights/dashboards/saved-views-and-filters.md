---
description: "Build a filtered view of requests, POs, or bills, save it, and share it with the people who need it."
icon: bookmark
---

# Saved views and filters

A saved view is a filtered, sorted, grouped list over one object type, stored under a name. Views are how most day-to-day reporting in Zip actually happens.

## Build and save a view

{% stepper %}
{% step %}
## Choose the object

Start from the list of requests, purchase orders, invoices, bills, payouts, or vendors. A view covers one object type; do not try to combine two.
{% endstep %}

{% step %}
## Apply filters

Filter on any field of the object, including intake form answers and custom fields. Combine filters with AND, and use grouped OR conditions where the logic requires it.
{% endstep %}

{% step %}
## Choose the columns

Add the columns the audience needs and remove the rest. A view with forty columns is an export, not a view.
{% endstep %}

{% step %}
## Group and sort

Group by the dimension that makes the list scannable, usually status, owner, or category. Sort by age when the view is an operational queue.
{% endstep %}

{% step %}
## Save and name it

Save the view with a name that says what it contains and who it is for: `Open software requests over threshold, IT procurement`.
{% endstep %}

{% step %}
## Share it

Share with individuals or groups, or make it available to everyone with access to the object. Recipients see the view filtered to the records their own scope allows.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Views respect the viewer's permissions, so sharing a view never grants access to records. Two people opening the same shared view can legitimately see different row counts.
{% endhint %}

## Relative dates

Use relative date filters rather than fixed ranges wherever the view will be reused: last 30 days, current quarter, current fiscal year. A view built with fixed dates is correct for one week and misleading afterwards.

## Views that earn their place

**Operational queues.** Work assigned to me, aging past a target, waiting on the requester. These get opened daily.

**Exception views.** Requests with no budget mapped, invoices with no matching PO, POs open with no activity for a long period, vendors with expired documents. These get opened weekly and are where most process problems surface first.

**Management views.** Spend by category for one department, grouped by vendor. These get scheduled rather than opened. See [Scheduled reports and exports](../distribution/scheduled-reports-and-exports.md).

## Maintaining views

Views break quietly when the underlying configuration changes. Two causes account for most of it:

**A retired field or category.** A filter referencing something that no longer exists stops matching, and the view returns fewer rows without saying why. Check views after any change published through [Intake management](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).

**An owner who has left.** Views shared by a departed user should be reassigned rather than left orphaned.

Review shared views once or twice a year and delete the ones nobody opens. A long list of stale views is the main reason people stop using the list at all.
