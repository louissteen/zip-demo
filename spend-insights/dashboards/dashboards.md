---
description: "The standard dashboards in Zip, the question each one answers, and how to read them without misinterpreting the numbers."
icon: gauge
---

# Dashboards

Dashboards are pre-built collections of charts and tables over the records Zip holds. Each one answers a specific question, and knowing which is which saves a lot of time.

## The standard dashboards

**Spend.** Where money is going: by category, vendor, department, subsidiary, and time. Sourced from approved requests, purchase orders, and bills. This is the dashboard finance asks for.

**Pipeline.** What is in flight: requests by stage, by age, and by value. Sourced from live approval chains. This is the dashboard procurement runs their week from.

**Cycle time.** How long the process takes, end to end and step by step. See [Cycle time and bottlenecks](../analysis/cycle-time-and-bottlenecks.md).

**Vendors.** Concentration and coverage: spend by vendor, vendors by category, onboarding and risk status. Pairs with [Vendor management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).

**Payables.** Invoices and bills by status and age, coding backlog, upcoming payment runs. The AP team's operational view.

**Savings.** Recorded negotiated outcomes by type and owner. See [Savings tracking](../analysis/savings-tracking.md).

## Reading the numbers correctly

The most common reporting mistake in procurement is comparing incompatible measures. Three distinctions matter.

**Requested, committed, and billed are different numbers.** Requested is what people asked for, committed is what was approved and ordered, billed is what vendors have invoiced. They diverge legitimately: requests get rejected, POs close short, and vendors invoice late.

**Request date and PO date are different dates.** A dashboard filtered by request date shows demand; one filtered by PO date shows commitment. A quarter can look busy on one and quiet on the other.

**Currency matters across entities.** Multi-subsidiary dashboards report in a reporting currency using the configured rate. The original transaction currency stays on the record and is available as a column.

{% hint style="warning" %}
Do not use the spend dashboard as a substitute for the general ledger. Zip reports on transactions that flowed through Zip, which is not the whole of company spend. See [Spend under management](../analysis/spend-under-management.md).
{% endhint %}

## Scope and permissions

A dashboard shows only the records the viewer can see. A department head with a scoped role sees their department's figures; a finance administrator with all-subsidiary scope sees everything.

This means two people can look at the same dashboard and see different totals, correctly. If a number is disputed, check the viewers' scopes first. Scope rules are described in [Roles and permissions](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/).

## Customizing

Standard dashboards can be filtered but not restructured. To change what is shown, build a saved view instead and pin it. See [Saved views and filters](saved-views-and-filters.md).

<details>

<summary>Choosing a dashboard by the question asked</summary>

**"What did we spend on software last quarter?"** Spend, filtered to the software category, by PO date.

**"Why is this request taking so long?"** Pipeline, filtered to the request, then open the chain.

**"Which reviews are slowing us down?"** Cycle time, grouped by step.

**"How exposed are we to this vendor?"** Vendors, filtered to the vendor, with contract and risk status.

**"What is AP working through?"** Payables, grouped by status and age.

</details>
