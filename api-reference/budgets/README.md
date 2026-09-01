---
description: "Read budget balances and check an amount before it is committed."
icon: chart-pie
---

# Budgets

A budget is an allocation of spend against a dimension for a fiscal period: a department, a cost center, a category, or a combination of them. Zip uses budgets to answer one question at approval time, which is whether the money is there.

Each budget separates three numbers. `allocated_amount` is what was set for the period. `committed_amount` is spend that is spoken for but not yet invoiced, from submitted [requests](../requests/README.md) and open [purchase orders](../purchase-orders/README.md). `actual_amount` is spend that has become a [bill](../bills/README.md). `remaining_amount` is the allocation less both.

The check available budget endpoint is the useful one for integrations. Give it an amount, a department, a cost center, a category, and a period, and it resolves which budget the spend would consume and reports whether enough remains, what the shortfall would be, and whether the amount would cross the budget's warning threshold.

Call it while a requester is still editing, not after they submit. A requester who sees a shortfall before submitting can split the line, change the period, or talk to the budget owner, rather than waiting for an approver to reject the request.

These endpoints are read only. Budgets are set in the product. See [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/) for how allocations, thresholds, and owners are configured.
