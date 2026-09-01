---
description: "Connect Zip to NetSuite so purchase orders, bills and vendor records stay in step with your ERP."
icon: arrows-rotate
---

# Connecting Zip to NetSuite

The NetSuite integration keeps Zip and your ERP aligned. Zip owns the intake and approval process, NetSuite remains the accounting system of record.

## What syncs

| Object | Direction | Notes |
| ------ | --------- | ----- |
| Vendors | Both | Zip creates vendors in NetSuite on approval, NetSuite updates flow back |
| Purchase orders | Zip to NetSuite | Created when a request is approved |
| Bills | Zip to NetSuite | Created when a bill is fully approved |
| Payments | NetSuite to Zip | Payment status flows back to close the loop |
| Chart of accounts | NetSuite to Zip | Departments, classes, locations and GL accounts |
| Subsidiaries | NetSuite to Zip | Used for multi-entity purchasing |

## Setting up the connection

{% stepper %}
{% step %}
## Create an integration record in NetSuite

In NetSuite, create an integration record with token-based authentication enabled. Note the consumer key and secret.
{% endstep %}

{% step %}
## Create a dedicated role and user

Give the role permissions for the record types being synced. A dedicated integration user makes the audit trail clear.
{% endstep %}

{% step %}
## Connect from Zip

In Zip, go to **Settings**, then **Integrations**, then **NetSuite**. Enter the account ID and the token credentials.
{% endstep %}

{% step %}
## Map your fields

Map Zip's departments, categories and subsidiaries to the equivalent NetSuite records. Zip flags anything it cannot map.
{% endstep %}

{% step %}
## Run a test sync

Sync a single test vendor and a test purchase order before enabling the integration for everyone.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Run the initial sync in a NetSuite sandbox account first. A mis-mapped GL account is much easier to fix before real transactions exist.
{% endhint %}

## Troubleshooting

<details>
<summary>A purchase order did not appear in NetSuite</summary>

Check the sync log under **Settings**, then **Integrations**, then **NetSuite**, then **Activity**. The most common causes are a missing subsidiary mapping, a vendor that is inactive in NetSuite, or a closed accounting period.

</details>

<details>
<summary>Chart of accounts values are missing in Zip</summary>

The chart of accounts refreshes on a schedule. Trigger a manual refresh from the integration settings, and confirm the integration role has permission to view the record type.

</details>

## Other ERP integrations

Zip also connects to SAP, Oracle, Coupa and Workday. The setup pattern is the same: create credentials in the ERP, connect from Zip, map fields, test with a single record.

## Related articles

* [How to access API documentation](using-apis/how-to-access-api-documentation.md)
* [ERP integration in the product documentation](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/purchase-orders/erp-integration)
