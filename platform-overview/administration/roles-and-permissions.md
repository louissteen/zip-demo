---
description: "How Zip decides what a user can see and change, using roles, scopes, and record-level access."
icon: user-shield
---

# Roles and permissions

Access in Zip is the combination of three things: the role a user holds, the scope that role applies to, and the records the user is personally attached to. All three have to be understood together, because a permission that looks broad is usually narrowed by scope.

## Roles

A role is a named bundle of permissions. Most deployments use a small set:

**Requester**: can submit requests, see their own requests, and respond to questions on them. This is the default role for everyone at the company.

**Approver**: can act on approval steps assigned to them, and can see the records those steps are on. Approvers do not automatically see every request in their department.

**Procurement operator**: can see and edit requests, manage vendors, issue and amend POs, and intervene in workflows.

**AP operator**: can code invoices, create and edit bills, apply vendor credits, and schedule payouts.

**Administrator**: can configure intake forms, workflows, budgets, integrations, and user access. Administrators can see all records in the scopes assigned to them.

{% hint style="warning" %}
Administrator is not the same as unrestricted. An administrator scoped to one subsidiary configures that subsidiary only. Grant an all-subsidiary administrator role sparingly, and review the list regularly in the [audit log](audit-log.md).
{% endhint %}

## Scope

Every role assignment carries a scope. Scope is normally expressed as a set of subsidiaries, and in larger deployments also as departments or categories.

The effect is multiplicative. An AP operator scoped to the EMEA entities sees invoices for those entities and nothing else. Give the same user a procurement operator role scoped to a single category, and they gain category-level rights without gaining anything extra in AP.

## Record-level access

Some access is not granted by configuration at all. It is earned by involvement:

- The requester on a request can always see it.
- Anyone named as an approver, reviewer, or watcher on a record can see that record while their step is live, and afterwards.
- Someone who is @-mentioned in a comment gains read access to that record.

This is how a legal reviewer sees a single contract request without holding a role that grants access to every request in the company.

## Sensitive requests

Requests can be marked confidential, which restricts visibility to the requester, named approvers, and administrators with the appropriate scope. Use it for people-related spend, acquisitions, and anything where the vendor name itself is the sensitive part.

<details>

<summary>Common access questions</summary>

**An approver says they cannot find a request.** Their step is probably not live yet. Approvers see records once their step activates, unless a role grants earlier visibility.

**A department head wants to see all their department's spend.** That is a reporting need, not an approval need. Give them a saved view in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/) rather than broadening their role.

**A contractor needs limited access.** Assign the narrowest role with a scope covering only the relevant subsidiary, and use an expiring account through your identity provider.

</details>

Roles and scopes can be assigned manually, or mapped from groups in your identity provider. See [SSO and provisioning](sso-and-provisioning.md).
