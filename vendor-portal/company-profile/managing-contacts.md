---
description: "Add colleagues to your portal account, assign roles, and control who receives what."
icon: users
---

# Manage contacts

Your company profile holds the people at your company who deal with this customer. Contacts determine who can sign in, what each person can see, and who receives which notifications.

## Contact roles

**Administrator.** Manages contacts, roles, and the company profile. Have at least two, so a single departure does not lock you out.

**Finance.** Views and changes bank details, submits invoices, and receives remittance advice. This is the only role that can see full account numbers.

**Sales or commercial.** Receives purchase orders and sourcing invitations, and responds to events.

**Security or compliance.** Receives and completes risk assessments and uploads certifications.

**Viewer.** Reads orders, invoices, and payments without changing anything. Useful for a controller or an account manager who needs visibility only.

One person can hold several roles. In a small company one person often holds all of them, which is fine as long as a second administrator exists.

## Adding a contact

{% stepper %}
{% step %}
## Open contacts

Go to **Company profile** and select **Contacts**. You need the administrator role.
{% endstep %}

{% step %}
## Invite the person

Select **Add contact** and enter their name and work email. Use individual addresses rather than shared mailboxes for people who sign in.
{% endstep %}

{% step %}
## Assign roles

Select the roles they need and no more. Bank details are visible only to the finance role, so assign that one deliberately.
{% endstep %}

{% step %}
## Send the invitation

They receive an invitation, create their own account with their own password and two-factor authentication, and appear as active once they sign in.
{% endstep %}
{% endstepper %}

## Shared mailboxes

A shared mailbox such as an accounts receivable address is useful as a notification recipient and a poor choice as a sign-in account, because you cannot tell who acted and you cannot use two-factor authentication properly.

Zip supports both: people sign in as themselves, and a shared address can be set as the recipient for remittance advice, purchase orders, or invoice notifications without being a login.

{% hint style="warning" %}
Remove contacts as soon as they leave your company. A former employee with the finance role can still see and change where your payments are sent. Review your contact list when someone leaves and at least once a quarter.
{% endhint %}

## Notification preferences

Each contact chooses which notifications they receive and how often, including immediate alerts or a daily summary. Some notifications cannot be turned off, such as an invoice returned with a query or a request for updated documents, because ignoring them stops you being paid.

## Notification addresses on the profile

Separately from individual contacts, your profile carries addresses for specific document types: where remittance advice is sent, where purchase orders are sent, and where invoice correspondence goes. Set these to the right team address so that documents do not depend on one person forwarding them.

If the wrong people are receiving your customer's documents, this is the setting to check first, along with the roles assigned to each contact.
