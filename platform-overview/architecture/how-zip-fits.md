---
description: "Where Zip sits between the people raising requests, the teams that approve them, and the systems of record that account for the spend."
icon: sitemap
---

# How Zip fits

Zip is an orchestration layer. It does not replace your ERP, your contract repository, or your security questionnaire tool. It sits in front of them and coordinates the work that has to happen before, and after, a record lands in those systems.

## The three sides

**Requesters** are the employees who need something bought: a software renewal, a consulting engagement, a set of laptops. They interact with one intake form and never need to know which teams are involved or what a GL code is.

**Reviewers and approvers** are the teams that have to weigh in: procurement, finance, legal, IT security, data privacy, tax. Each of them has an opinion on a subset of requests. Zip's job is to work out which subset, in what order, and to collect their decisions without anyone chasing anyone in email.

**Systems of record** are where the outcome has to live: NetSuite, SAP, Oracle, Coupa, or Workday for financial records, your CLM for executed agreements, your identity provider for who works here. Zip writes to these systems and reads back from them so the two stay aligned.

## What Zip owns

Zip owns the process and the record of the process. Concretely, that means:

- The intake experience and the request record itself.
- The approval chain: who was asked, what they said, when, and on what basis.
- The purchase order, from creation through close, and its sync status with the ERP.
- Invoice capture, coding, and bill approval.
- Payment scheduling and payout execution where the Global Payments add-on is in use.
- The vendor record as it is used for buying, including onboarding state and risk status.

## What Zip defers to

Zip does not become the general ledger. Period close, journal entries, revenue recognition, and statutory reporting stay in the ERP. Zip pushes the transactions and reads back the master data it needs, such as chart of accounts, subsidiaries, tax codes, and amortization schedules.

{% hint style="info" %}
Master data flows one way in most deployments. Subsidiaries, departments, and GL codes are maintained in the ERP and synced into Zip, so a code that does not exist in the ERP cannot be selected on a Zip request.
{% endhint %}

## Why the layering matters

Because Zip holds the process, a single request can trigger work in several systems without the requester coordinating any of it. One intake submission can open a security review in [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/), start a vendor onboarding in [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/), route a redline through [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/), and still end as a single purchase order in the ERP.

It also means the audit trail is continuous. When someone asks in twelve months why a vendor was approved at that amount, the answer is on one record rather than scattered across four tools and a mail archive.

Next, see [Core objects](core-objects.md) for the records Zip creates and how they link together.
