---
description: "Design the approval logic behind every request, PO, and bill: triggers, conditions, steps, escalation, and how to test a change before it goes live."
icon: diagram-next
---

# Workflow engine

The workflow engine decides who has to weigh in on a record, in what order, and what happens when they do not respond. It runs on purchase requests, on bills, and on any custom object you build in [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/).

A workflow is a set of rules, not a fixed chain. Two requests submitted on the same form can take completely different paths depending on amount, category, vendor risk, and subsidiary. This space covers how those rules are expressed, how to build and test them, and how to keep approvals moving when an approver is unavailable.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Anatomy of a workflow</strong></td><td>Triggers, conditions, actions, and steps.</td><td><a href="concepts/workflow-anatomy.md">concepts/workflow-anatomy.md</a></td></tr><tr><td><strong>Conditions and branching</strong></td><td>How Zip decides which steps apply to a record.</td><td><a href="concepts/conditions-and-branching.md">concepts/conditions-and-branching.md</a></td></tr><tr><td><strong>Approval steps</strong></td><td>Sequential, parallel, and quorum-based approvals.</td><td><a href="concepts/approval-steps.md">concepts/approval-steps.md</a></td></tr><tr><td><strong>Build a workflow</strong></td><td>Create a workflow from scratch, step by step.</td><td><a href="building/build-a-workflow.md">building/build-a-workflow.md</a></td></tr><tr><td><strong>Escalation and delegation</strong></td><td>Keep approvals moving when someone is unavailable.</td><td><a href="building/escalation-and-delegation.md">building/escalation-and-delegation.md</a></td></tr><tr><td><strong>Step SLAs</strong></td><td>Set response targets and act when they are missed.</td><td><a href="building/step-slas.md">building/step-slas.md</a></td></tr><tr><td><strong>Test and publish</strong></td><td>Simulate a workflow against real records before release.</td><td><a href="release/test-and-publish.md">release/test-and-publish.md</a></td></tr></tbody></table>
