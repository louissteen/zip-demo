---
description: "Deliver a saved view on a schedule, and get data out of Zip for the systems and people that need it elsewhere."
icon: paper-plane
---

# Scheduled reports and exports

Most reporting should arrive without anyone logging in. Schedule the views your audience needs, and use exports for the cases where data has to leave Zip.

## Schedule a report

{% stepper %}
{% step %}
## Start from a saved view

Scheduling works from a saved view, so build and share the view first. See [Saved views and filters](../dashboards/saved-views-and-filters.md).
{% endstep %}

{% step %}
## Create the schedule

Select **Schedule** on the view. Choose the frequency and the send time, using the time zone of the audience rather than yours.
{% endstep %}

{% step %}
## Choose the recipients

Add individuals or groups. Recipients receive the view filtered to the records their own permissions allow, so one schedule can serve many budget owners without leaking anything.
{% endstep %}

{% step %}
## Choose the format

Send a summary in the message body, an attached file, or a link back to the live view. Prefer the link for anything people will act on, so they work from current data.
{% endstep %}

{% step %}
## Send a test

Send yourself a test delivery and check the row count, the columns, and the relative date range.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Use relative date filters in any scheduled view. A schedule built on a fixed date range sends the same rows every week and quietly stops being read.
{% endhint %}

## Choosing a cadence

Match the cadence to the decision the report supports. Operational queues are daily or not at all. Budget positions are monthly. Coverage and savings metrics are quarterly.

Fewer, better-targeted reports get read. A weekly report to a wide distribution list is a report nobody owns.

## Exports

Exports produce a file from a view or a dashboard, with the filters and columns as configured at the time you run it.

Use exports for auditor samples, for one-off analysis in a spreadsheet, and for loading into a system that has no integration. Note the filter criteria alongside any file you hand to an auditor, so the sample can be reproduced.

{% hint style="warning" %}
Exported files leave Zip's permission model behind. A file containing vendor pricing or confidential request detail is only as protected as the place it is stored. Export the narrowest set of columns that answers the question.
{% endhint %}

## When not to export

If you are exporting the same data on a recurring basis into another system, use the API instead. Scheduled exports into a warehouse are fragile, arrive late, and drift out of sync. See the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).

If you are exporting because a view cannot express what you need, check whether a custom field or object would solve it. See [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/).

## Auditing delivery

Scheduled sends are recorded, so you can confirm a report went out and to whom. Failed deliveries, usually a deactivated recipient, are surfaced on the schedule so they can be cleaned up rather than silently dropped.
