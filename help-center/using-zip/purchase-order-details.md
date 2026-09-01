---
description: "Read every field on the purchase order details page, understand PO statuses, and learn what changes when a PO is sent, billed or closed."
icon: file-invoice
---

# Purchase order details

The purchase order details page is where you check what a PO covers, how much of it has been billed, and whether the vendor has received it. Open it from the **Purchase Orders** page by selecting a PO number.

<figure><img src="../images/po-details.png" alt="The purchase order details page showing the summary panel, vendor details and purchase terms" width="820"></figure>

## Page layout

The page is split into two areas:

* The **summary panel** on the left, which holds the PO number, status, amounts and the request it came from
* The **detail tabs** on the right, which hold vendor and buyer information, purchase terms and billing details

### The summary panel

The summary panel gives you the state of the PO at a glance:

1. **Total, net billed and open amounts**
   * **Total** is the full value of the PO
   * **Net billed** is the amount already covered by approved bills, less any applied vendor credits
   * **Open** is what remains available to bill against
2. **Request and requester**
   * The originating purchase request, as a link back to the request record
   * The person who submitted it
3. **Dates and version**
   * **PO created** is the date the PO was generated from the approved request
   * **Sent status** tells you whether the vendor has received it
   * **Version** increments each time the PO is amended and re-sent
4. **Accounting attributes**
   * Department, location, category and subcategory
   * These are inherited from the request and are used for GL coding

{% hint style="info" %}
Net billed and open always sum to the total. If they do not, a bill is still pending approval and has not yet been counted.
{% endhint %}

## Purchase order statuses

| Status | What it means | Can you bill against it |
| ------ | ------------- | ----------------------- |
| Open | The PO is active and has remaining balance | Yes |
| Closed | The PO has been fully billed or manually closed | No |
| Cancelled | The PO was voided before use | No |

## Vendor and buyer details

The **Overview** tab shows the vendor's billing address and contacts alongside your own billing and ship-to addresses. Select **View vendor record** to open the full vendor profile, where you can check onboarding status, banking details and tax forms.

Each detail card has an **Edit mode** toggle. Turning it on lets you correct the address or contacts on this PO without changing the underlying vendor record.

{% hint style="warning" %}
Editing the vendor billing address here affects this purchase order only. To correct the address everywhere, update the vendor record instead.
{% endhint %}

## Purchase terms

Purchase terms carry the commercial detail of the order:

* **Currency** and **total amount**
* **Subsidiary**, which determines which entity is buying
* **Start date**, **end date** and **payment frequency** for recurring orders
* **Payment terms**, inherited from the vendor agreement where one exists
* **Quote number**, **manager** and any custom PO fields your organization has configured

## Sending a purchase order to a vendor

{% stepper %}
{% step %}
## Review the PO

Confirm the amounts, the ship-to address and the purchase terms are correct.
{% endstep %}

{% step %}
## Select Send to vendor

The button is in the upper right of the page. Zip generates a branded PDF and emails it to the vendor's PO contacts.
{% endstep %}

{% step %}
## Confirm delivery

The **Sent status** field changes from **Not sent** to the date it was sent. The vendor can also download the PO from the vendor portal.
{% endstep %}
{% endstepper %}

## Where a purchase order appears elsewhere

The tables below show the other places in Zip where this PO is visible. Select a thumbnail to open the article for that page.

<table><thead><tr><th width="180">Page</th><th width="140">Thumbnail</th><th>What it shows about this PO</th><th>Article</th></tr></thead><tbody><tr><td><strong>Invoice details</strong></td><td><a href="../for-vendors/submitting-an-invoice.md"><img src="../images/invoice-details.png" alt="Invoice details page" width="120"></a></td><td>The PO match panel, remaining balance and other matched bills</td><td><a href="../for-vendors/submitting-an-invoice.md">Submitting an invoice</a></td></tr><tr><td><strong>Bills</strong></td><td><a href="approving-a-bill.md"><img src="../images/bills-list.png" alt="Bills list page" width="120"></a></td><td>The PO number against each bill awaiting approval</td><td><a href="approving-a-bill.md">Approving a bill</a></td></tr><tr><td><strong>Schedule payouts</strong></td><td><a href="../for-vendors/payment-status-and-remittance.md"><img src="../images/schedule-payouts.png" alt="Schedule payouts page" width="120"></a></td><td>The PO number on each bill included in a payout group</td><td><a href="../for-vendors/payment-status-and-remittance.md">Payment status and remittance</a></td></tr></tbody></table>

## Billing against a purchase order

When a vendor invoice arrives, Zip matches it to the PO automatically wherever it can. The matched amount is deducted from the open balance.

<figure><a href="approving-a-bill.md"><img src="../images/invoice-details.png" alt="An invoice matched to a purchase order, showing zero dollars remaining" width="620"></a></figure>

The invoice above has consumed the full PO balance, so **Open** on the PO drops to zero and the PO moves to **Closed**. Select the image to read how the resulting bill is approved.

## Linking to another article

To reference another help center article from a PO description or a comment:

1. Select the text you want to turn into a link
2. Select the link icon in the toolbar, or press **Cmd + K** on macOS or **Ctrl + K** on Windows
3. Paste the article URL, or start typing the article title and choose it from the results
4. Press **Enter**

Links created this way resolve to the reader's own help center, so they keep working when the article is moved or renamed.

## Related articles

* [Creating a purchase request](creating-a-purchase-request.md)
* [Approving a bill](approving-a-bill.md)
* [How to access API documentation](../integrations/using-apis/how-to-access-api-documentation.md)
* [Purchase orders in the product documentation](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/purchase-orders/purchase-order-details)
