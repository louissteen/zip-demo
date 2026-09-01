---
description: "Set up a budget, load its amounts, name its owner, and activate it for the period."
icon: circle-plus
---

# Create a budget

Create budgets after your subsidiaries, departments, and chart of accounts have synced from the ERP. Budgets reference those dimensions, so they cannot be mapped correctly until the dimensions exist.

{% stepper %}
{% step %}
## Create the budget

Go to **Budgets** and select **New budget**. Give it a name your approvers will recognize, usually the owning team plus the spend area: `Marketing, agency and creative`.
{% endstep %}

{% step %}
## Set the subsidiary and currency

Choose the subsidiary. The currency defaults from it and determines how line items in other currencies are converted.
{% endstep %}

{% step %}
## Define the period

Choose the fiscal year and the granularity: annual, quarterly, or monthly. See [Budget periods](budget-periods.md) for how phasing and rollover behave.
{% endstep %}

{% step %}
## Map the dimensions

Attach the budget to the departments, categories, and GL codes whose spend it should track. See [Mapping budgets to your org](mapping-budgets.md).
{% endstep %}

{% step %}
## Load the amounts

Enter the amount for each period, or import them. Most organizations import from the planning spreadsheet finance already maintains rather than typing figures in twice.
{% endstep %}

{% step %}
## Name an owner

Set the budget owner. The owner receives threshold alerts, appears as the assignee when a workflow adds a budget approval step, and is the person a requester is pointed at when they are over.
{% endstep %}

{% step %}
## Choose the enforcement level

Set the budget to warn, require approval, or block. See [Soft and hard limits](../controls/soft-and-hard-limits.md). Start with warn for a new budget.
{% endstep %}

{% step %}
## Activate

Activate the budget. It starts tracking from activation; it does not retroactively consume against requests approved before that point unless you import opening balances.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Activating mid-period without loading opening consumption makes a half-spent budget look untouched. Either activate at the start of a period, or import the consumed-to-date figure so the remaining number is honest.
{% endhint %}

## Importing amounts

The import expects one row per budget per period, with the dimension values, the period, and the amount. Validation runs before anything is written, and rejects rows referencing a department, GL code, or subsidiary that does not exist in Zip.

Import is also how you revise. Re-importing replaces the amounts for the periods included in the file and leaves the others alone, so a mid-year reforecast can cover the remaining quarters only.

## After creation

Check the budget on a real request. Submit a test request coded to the mapped department and GL code, confirm the budget is identified, and confirm the amount is deducted where you expect. Then withdraw it.

If the budget is not identified, the mapping is too narrow or the request is coding to a dimension you did not map. See [Budget checks during intake](../controls/budget-checks-in-intake.md).
