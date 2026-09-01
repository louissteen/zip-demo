---
description: "Find a request, see who is holding it, and move it along."
icon: magnifying-glass-chart
---

# Track a request

Once a request is submitted, everyone involved can see the same view of it. Requesters do not have to chase approvers by email, and approvers do not have to guess what has already happened.

## Find a request

The **Requests** page lists every request you have permission to see. Use the tabs to switch between requests you raised, requests waiting on you, and all requests. Filter by status, vendor, department, amount, or date, and save a filter set as a view if you use it regularly.

You can also search by request number, vendor name, or any word in the title or description.

## Read the request detail page

The detail page has three parts that matter for tracking.

**Header.** Request number, status, vendor, amount, and the requester. The current approval step and the people assigned to it are shown here.

**Approval chain.** Every step in order, with its approvers and its state. Completed steps show who approved and when. The active step is highlighted. Steps that have not started yet are shown so you can see what is still to come.

**Activity.** A running log of submissions, approvals, edits, comments, and system actions such as a risk assessment starting. The log is append only, which is what makes it useful for audit.

## Move a stalled request

{% stepper %}
{% step %}
## Check who is actually assigned

Open the active approval step. If a step is assigned to a group, any member can act on it. If it is assigned to one person who is out of office, note their delegate.
{% endstep %}

{% step %}
## Send a nudge

Select **Remind** on the active step. Zip re-sends the approval notification to everyone currently assigned, in email and in Slack or Teams if connected.
{% endstep %}

{% step %}
## Ask a question in the comments

Add a comment and @mention the approver. Comments are part of the request record, so the answer stays with the request instead of in a private thread.
{% endstep %}

{% step %}
## Escalate

If the step has an escalation policy, an administrator or the request owner can reassign it to a delegate or to the approver's manager. The original assignment stays visible in the activity log.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Ask the [AI Procurement Concierge](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/) where a request is in plain language, for example "what is holding up my renewal for the design tool". It answers from the same data the detail page shows.
{% endhint %}

## Watch a request you did not raise

Select **Follow** on any request you can see. Followers get the same status notifications as the requester without being added to the approval chain. Category owners often follow requests in their category so they hear about a purchase before the PO is issued.
