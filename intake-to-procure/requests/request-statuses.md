---
description: "What each purchase request status means and how a request moves between them."
icon: signal-stream
---

# Request statuses

Every purchase request in Zip carries a status. The status answers one question: what has to happen next, and who has to do it. Statuses are set by Zip as the request moves through its workflow, not chosen by hand.

## The status lifecycle

```mermaid
stateDiagram-v2
    [*] --> Draft
    Draft --> InReview: Submitted
    InReview --> NeedsInfo: Approver requests changes
    NeedsInfo --> InReview: Requester resubmits
    InReview --> Approved: Final approver approves
    InReview --> Rejected: Approver rejects
    InReview --> Canceled: Requester withdraws
    Approved --> Ordered: PO issued
    Ordered --> Closed: Fully received and billed
    Rejected --> [*]
    Canceled --> [*]
    Closed --> [*]
```

## What each status means

**Draft.** The requester has started a request but has not submitted it. No one else can see it and no approvals have been triggered.

**In review.** The request is moving through its approval chain. One or more approvers are assigned at any given time. The request detail page shows the current step and who is holding it.

**Needs info.** An approver sent the request back to the requester with a question or a change. Approvals are paused. When the requester resubmits, the chain resumes at the step that sent it back, and earlier approvals are preserved unless the edit changed a field that routing depends on.

**Approved.** Every required approver has approved. The request is cleared to buy. Depending on your configuration, Zip either creates a purchase order automatically or waits for a buyer to issue one.

**Rejected.** An approver declined the request. Rejected requests are terminal. To pursue the purchase, the requester raises a new request, usually referencing the rejected one.

**Canceled.** The requester or an administrator withdrew the request before it was approved.

**Ordered.** A purchase order has been issued against the approved request. From here the record continues into receiving and invoicing.

**Closed.** No further activity is expected. The PO has been fully received and billed, or a buyer closed it manually.

{% hint style="warning" %}
Editing an approved request does not silently keep its approvals. If you change the amount, vendor, category, or any other field that routing conditions read, Zip re-evaluates the chain and returns the request to **In review** for the approvers the new values require.
{% endhint %}

## Statuses and reporting

Status is one of the main filters on the **Requests** page and in reporting. Cycle time is measured between status changes, so a request sitting in **Needs info** for a week counts against the requester rather than against an approver. Procurement teams commonly track time in **In review** by approval step to find the stage that slows requests down.

For how these statuses feed spend reporting and savings, see [Spend Insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).
