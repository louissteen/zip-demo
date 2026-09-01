---
description: "Find Zip's API documentation from inside your Zip account, and learn what each tab of the developer reference covers."
icon: code
---

# How to Access API Documentation

Zip's API documentation is available directly from your Zip account. You do not need a separate developer login, but your user must have the API access permission enabled by an administrator.

## Opening the API documentation

{% stepper %}
{% step %}
## Sign in to Zip

Log in to your Zip account at your organization's Zip URL.
{% endstep %}

{% step %}
## Open the help menu

Select the question mark icon in the upper right corner of any page.
{% endstep %}

{% step %}
## Select API Documentation

Choose **API Documentation** from the menu. The reference opens in a new browser tab.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
If you do not see **API Documentation** in the help menu, your user does not have API access. Ask a Zip administrator to enable it on your profile.
{% endhint %}

## What you will find

The reference is organized into the following areas:

1. **Getting started**
   * Authentication and API keys
   * Base URLs for production and sandbox
   * Conventions for pagination, filtering and errors
2. **Resources**
   * Requests, purchase orders, invoices and bills
   * Vendors and vendor contacts
   * Payments and payout groups
3. **Webhooks**
   * The event catalog
   * Signature verification
   * Retries and replay

## Generating an API key

API keys are managed by administrators under **Settings**, then **Developers**, then **API keys**. Each key is scoped to a set of resources and can be restricted to a single subsidiary.

{% hint style="warning" %}
Treat an API key like a password. Store it in a secrets manager rather than in source control, and rotate it if you believe it has been exposed.
{% endhint %}

## Related articles

* [Purchase order details](../../using-zip/purchase-order-details.md)
* [Connecting Zip to NetSuite](../netsuite.md)
* [Full API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/)
