---
description: "Where executed contracts live, what the contract record holds, and who can see it."
icon: box-archive
---

# The contract repository

The repository holds every contract your organization has, executed or in flight, with the structured data extracted from each one. It is the answer to questions that are otherwise a search of shared drives and inboxes: what have we signed with this vendor, what does it commit us to, and when does it end.

## The contract record

A contract record carries four things.

**The documents.** Every version, from first draft to executed original, in order, with who uploaded each and when. The executed version is marked.

**The extracted terms.** Parties, dates, value, and the legal positions pulled out during review, each linked back to its source passage.

**The relationships.** The vendor record, the intake request that started it, the sourcing event that awarded it, the purchase orders issued against it, the risk assessments attached to it, and any parent agreement it hangs off.

**The history.** Approvals, reviewer comments, negotiation rounds, amendments, and any change to a field after execution.

## Contract families

Agreements do not stand alone. A master services agreement has statements of work under it. A master subscription agreement has order forms. An amendment modifies a parent.

Zip models this as a family. The parent holds the legal terms, the children hold the commercials, and a child inherits its parent's positions unless it overrides them. Opening an order form shows the terms that actually govern it, including the ones written in the master three years earlier.

{% hint style="info" %}
When you load legacy contracts, load parents before children. A statement of work uploaded without its master agreement has no legal terms attached, and it is easy to conclude from the record that none were agreed.
{% endhint %}

## Search

Search covers document text and extracted fields together. You can search for a phrase in the body of an agreement, and you can filter on structure: contracts with a given counterparty, expiring in a window, above a value, with a specified governing law, with auto-renewal, or with a liability cap below a figure.

Saved searches can be turned into views for a team, for example every agreement with a data processing addendum, or every contract in a region expiring in the next two quarters.

## Permissions

Contracts are not visible to everyone by default. Access is granted by role, by department, and by explicit assignment on an individual contract. A business owner sees their own agreements, a category manager sees their category, legal sees everything, and a highly sensitive agreement can be restricted to a named list.

Search respects permissions. A contract you cannot open does not appear in your results, including in aggregate counts.

## Getting contracts in

New contracts arrive through the request process and file themselves on execution. Existing contracts arrive by bulk upload, by connecting a document repository so Zip ingests what is already there, or by an integration with your e-signature provider that files completed envelopes automatically.

For programmatic loading and export, see the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).
