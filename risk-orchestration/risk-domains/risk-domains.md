---
description: "The risk domains Zip assesses, what each one looks at, and who owns it."
icon: layer-group
---

# Risk domains

A risk domain is an area of exposure with its own reviewers, its own questions, and its own findings. Domains run in parallel, and most vendors engage more than one. Zip ships a common set and your administrators can add domains specific to your industry.

{% tabs %}
{% tab title="Security" %}
Owned by information security. Engaged when a vendor holds company or customer data, connects to internal systems, or develops software you deploy.

The assessment covers access control and authentication, encryption at rest and in transit, network and infrastructure security, secure development practices, vulnerability and patch management, logging and monitoring, incident response and breach notification commitments, subprocessor and supply chain controls, and physical security where relevant.

Evidence carries a lot of weight here. A current independent audit report or certification covering the product in scope satisfies most of the control set, and the reviewer's attention goes to what it does not cover.
{% endtab %}

{% tab title="Privacy" %}
Owned by the privacy or data protection function. Engaged whenever the vendor processes personal data on your behalf.

The assessment establishes what categories of personal data are involved, whose data it is, the lawful basis, where the data is stored and processed, which subprocessors are used, the international transfer mechanism, retention and deletion practices, how data subject requests are supported, and the security measures specific to that data.

The output is usually a data processing agreement with the right terms, and, where the processing is high risk, a data protection impact assessment. Privacy findings frequently become contract clauses rather than technical remediation, so this domain and [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/) are closely linked.
{% endtab %}

{% tab title="Financial" %}
Owned by finance or procurement. Engaged for vendors that are material to spend or critical to operations.

The assessment looks at financial viability, ownership and funding, concentration risk on your side and theirs, insurance coverage, and where the vendor's failure would leave you. Much of this can be automated from external data providers rather than asked of the vendor.

Financial risk drives contract terms more than technical remediation: escrow, step-in rights, exit assistance obligations, and payment terms.
{% endtab %}

{% tab title="Other domains" %}
**Business continuity.** Recovery objectives, tested continuity plans, and dependency on the vendor for a critical process.

**Compliance and regulatory.** Sanctions and denied party screening, anti-bribery and corruption, modern slavery, and any sector-specific regulatory obligation that flows down to suppliers.

**Environmental and social.** Emissions data, environmental certifications, labor practices, and supplier diversity, where your organization reports on these.

**AI usage.** Whether the vendor uses AI in the service, what data feeds it, whether your data trains shared models, and what human oversight exists. Increasingly its own domain rather than a section of the security questionnaire.
{% endtab %}
{% endtabs %}

## How domains interact

Domains are assessed independently but scored together. A vendor can pass security comfortably and still be unacceptable on financial viability.

Findings from one domain can trigger work in another. A privacy finding about international transfers becomes a contract clause. A security finding about missing encryption may be accepted temporarily with a compensating control that business continuity has to validate.

{% hint style="info" %}
Each domain needs a named owner who can make a decision. A domain with a queue but no decision maker becomes the step every assessment waits on, and the business learns to route around it.
{% endhint %}

## Configuring domains

Administrators define each domain's questionnaire, its reviewer group, the conditions that engage it, its scoring model, and its reassessment interval. Adding a domain is a real cost to vendors and to reviewers, so add one when it has an owner and a decision it will drive.
