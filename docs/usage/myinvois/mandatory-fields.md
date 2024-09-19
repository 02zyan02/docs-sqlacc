---
sidebar_position: 2
title: Mandatory Fields
description: update fields for e-invoice usage
slug: /usage/myinvois/mandatory-fields
tags: ["SQL Account", "Usage", "MyInvois", "E-Invoice", "Customer", "Stock"]
---

Before issuing an e-Invoice, you will need to make sure some mandatory fields is updated correctly.

## Update Customer Info

1. Go to **Customer** > **Maintain Customer** > **New** or **Edit** an existing customer.
2. Fill in the mandatory fields as shown below.

    ![maintain-customer-general](../../../static/img/myinvois/guide/maintain-customer-general.png)

3. Click on **Tax** tab, and fill in customer tax info according to the guide in next section.

### Local Business (Companies registered with local authorities)

If you customers are a registered entity in Malaysia (e.g.: SSM registered), you must fill in the BRN & TIN of the customer in order to issue e-Invoice to the buyer.

    ![maintain-customer-tax](../../../static/img/myinvois/guide/maintain-customer-tax.png)

### Individual / Foreign Buyer

In facilitating a more efficient e-Invoice issuance process as well as to ease the burden of individuals in providing their Tax Identification Number (TIN) and identification number details, IRBM provides the following concession to individuals:

1. For Malaysian Individuals to provider either:
   1. TIN only
   2. MyKad / MyTentera identification number only
   3. Both TIN and MyKad / MyTentera identification number
2. For non-Malaysian individuals to provide either:
   1. TIN only (TIN assigned by IRBM or use General TIN **EI00000000020**)
   2. Both TIN and BRN of foreign company
   3. Both TIN and passport number / MyPR / MKAS identification number

For Malaysian Individuals:
|Scenario|In SQL Account|
|---|---|
|TIN only|**ID Type**: NRIC, **ID Value**: Leave Empty, **TIN**: Buyer TIN|
|MyKad only|**ID Type**: NRIC, **ID Value**: Buyer NRIC, **TIN**: General Public **EI00000000010** |
|Both TIN & MyKad|**ID Type**: NRIC, **ID Value**: Buyer NRIC, **TIN**: Buyer TIN|

For non-Malaysian Individuals:

|Scenario|In SQL Account|
|---|---|
|TIN only|**ID Type**: Passport, **ID Value**: Leave Empty, **TIN**: Buyer TIN or General TIN **EI00000000020**|
|Both TIN & BRN of Foreign Company|**ID Type**: BRN, **ID Value**: Buyer BRN, **TIN**: Buyer TIN or General TIN **EI00000000020**|
|Both TIN & Passport|**ID Type**: Passport, **ID Value**: Buyer Passport Number, **TIN**: Buyer TIN or General TIN **EI00000000020**|

**Reference:**

1. List of ID Type in Maintain Customer:

    ![maintain-customer-tax-idtype](../../../static/img/myinvois/guide/maintain-customer-tax-idtype.png)

2. List of General TIN in Maintain Customer:

    ![maintain-customer-tax-tin](../../../static/img/myinvois/guide/maintain-customer-tax-tin.png)

### Batch TIN Lookup

:::info
This feature enables users to **quickly look up missing New BRN/TIN information for customers** and is exclusively available to those with an active SQL Account license
:::

1. Navigate to **Customer** > **Maintain Customer**.

    ![batch-tin-lookup-1](../../../static/img/myinvois/guide/batch-tin-lookup-1.png)

2. Right click on the menu bar (located at the right side of the window), select **TIN Lookup**.

    ![batch-tin-lookup-2](../../../static/img/myinvois/guide/batch-tin-lookup-2.png)

3. In the **Tin Lookup** window, you will be able to view all of your customers details such as *Old BRN, New BRN, TIN* and etc. Click on the **🔍** to do a quick lookup on the missing fields, when you are done, click **Save** to apply.

    ![batch-tin-lookup-3](../../../static/img/myinvois/guide/batch-tin-lookup-3.png)

## Update Stock Item

IRBM (LHDN) has introduced [Classification Codes](https://sdk.myinvois.hasil.gov.my/codes/classification-codes/) to define the category of products or services being billed as a result of a commercial transaction.

1. Go to **Stock** > **Maintain Stock Item** > **Edit** stock
2. Update the classification accordingly.

    ![maintain-stock-classification](../../../static/img/myinvois/guide/maintain-stock-classification.png)

3. Repeat Step 1-2 for all stocks.

:::info
You can also override the stock item classification codes during sales invoice entry.

![sales-invoice-classification](../../../static/img/myinvois/guide/sales-invoice-classification.png)
:::
