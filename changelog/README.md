---
description: "Release notes for the Zip platform. Zip ships on the fourth Tuesday of each month."
icon: rectangle-history
---

# Release notes

Zip publishes a release on the fourth Tuesday of each month. Each entry lists what changed, which product area it affects, and where to read more.

Administrator action is called out where a release needs configuration before it takes effect.

{% updates %}

{% update title="August 2026 release" date="2026-08-25" tags="superagents,governed-ai,procure-to-pay" %}

**Observation mode for Superagent guardrails.** You can now test a guardrail change against recent records before it goes live. Zip reports what the agent would have done and where it would have stopped, without changing anything. Available on every agent type from the **Guardrails** tab. See [Guardrails and approval boundaries](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/).

**Run replay.** Any agent run can be re-evaluated against the agent's current configuration to confirm a fix, or to check whether a past error is still reachable. Replay never touches the record.

**Version filtering in the AI activity log.** Filter agent runs and Concierge answers by model, prompt, or tenant configuration version. This is the query to run after a rollback. See [Compliance evidence](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

**Tax code inheritance on partial invoices.** Invoices billing against part of a purchase order now inherit tax treatment from the PO line rather than the PO header, which removes a common coding exception on multi-line orders. See [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).

{% endupdate %}

{% update title="July 2026 release" date="2026-07-28" tags="concierge,intake,workflow-engine" %}

**Concierge answers cite their sources.** Every Concierge answer now names the policy section or record it came from, and requesters can open the source directly. Answers with no sufficient source hand off rather than composing a response. See [What the Concierge answers](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/).

**Reusable replies from handoffs.** When a team member answers a handed-off question, they can mark the reply reusable. Reusable replies appear as candidate answers for administrators to review and publish.

**Conditional sections on intake forms.** Intake forms can show or hide whole sections based on earlier answers, rather than only individual fields. Long forms for regulated categories are noticeably shorter for requesters who do not need them. See [Intake management](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).

**Approval chain preview.** Requesters see the approval path their submission will follow before they submit, including the conditions that produced it. See the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

{% endupdate %}

{% update title="June 2026 release" date="2026-06-23" tags="governed-ai,superagents,risk" %}

**AI policy scoping by entity and category.** AI policies can now be scoped to subsidiaries, departments, regions, and categories, with the most restrictive applicable rule taking precedence. Customers running different obligations by region no longer need a single policy with a list of exceptions. See [AI policy definition](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

**Field-level exclusions for custom objects.** Fields created in [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/) can be marked sensitive and excluded from model context, matching the treatment of standard fields.

**Risk review agent reuses prior assessments.** The risk review agent now pulls a vendor's previous assessments into the package and answers reviewer questions a prior review already settled. Reviewers still make every determination. See [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/).

**Administrator action required.** Entity scoping is off until you set it. Existing policies continue to apply organization-wide until scoped.

{% endupdate %}

{% update title="May 2026 release" date="2026-05-26" tags="sourcing,contracts,vendor-management" %}

**Structured bid comparison.** Sourcing event responses are normalized into a comparable structure so that vendors answering in different formats can be read side by side. Award decisions remain human. See [Sourcing](https://app.gitbook.com/s/yWPKTXf10NGJgEVmE6Ok/).

**Renewal requests open ahead of auto-renewal dates.** The contract agent opens a renewal request in advance of an auto-renewal date and attaches the current terms, prior spend, and the extracted renewal clause. See [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/).

**Vendor record consolidation.** Duplicate vendor records can be merged with their contracts, purchase orders, and spend history preserved against the surviving record. See [Vendor Management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).

{% endupdate %}

{% update title="April 2026 release" date="2026-04-28" tags="procure-to-pay,budgets,spend-insights" %}

**Variance tolerances by category.** Invoice-to-PO variance tolerances can be set per category rather than only globally, so professional services and software renewals no longer share a threshold. See [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).

**Committed spend on budget checks.** Budget checks at approval now include committed spend from open purchase orders alongside actuals, so approvers see the full position rather than only what has been billed. See [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/).

**Cycle time by approval step.** Spend insights reports time spent at each approval step, which makes a single slow step visible instead of an overall average. See [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).

**Combined payouts across subsidiaries.** Payments to the same vendor across subsidiaries in one currency can be combined into a single payout where your configuration allows it.

{% endupdate %}

{% update title="March 2026 release" date="2026-03-24" tags="supplier-onboarding,vendor-portal,api" %}

**Document chasing in the vendor portal.** The vendor onboarding agent requests missing documents directly through the vendor portal and tracks what is outstanding, instead of relying on email follow-up from your team. Bank detail changes remain a human decision at every step. See [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

**Onboarding status visible to vendors.** Vendors see which onboarding items are complete, which are pending review, and which need action from them. See the [Vendor Portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/).

**Webhooks for agent run outcomes.** Subscribe to run completion, run stopped, and checkpoint reached events to drive your own downstream systems. See the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).

{% endupdate %}

{% update title="February 2026 release" date="2026-02-24" tags="superagents,governed-ai,concierge" %}

**Superagents general availability.** The intake, vendor onboarding, invoice and bill, risk review, contract, and sourcing agents are available to all customers. Each agent runs as its own service role with its own scope and action list, and every run writes an audit record. See [Superagents](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/).

**Human checkpoints enforced at the platform level.** Approving spend, changing vendor bank details, releasing payment, awarding a sourcing event, executing a contract, and overriding a failed risk assessment cannot be performed by an agent under any configuration. See [Human checkpoints](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

**Concierge coverage reporting.** Administrators can see what the Concierge answered, what it deflected, and why, with the topics that have no configured source listed for policy authors. See [Coverage reporting](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/).

**Administrator action required.** Agents are off by default. Enable one agent at a time and review its intervention rate for a full cycle before enabling the next.

{% endupdate %}

{% endupdates %}
