<!-- loiodc119223736d4e5f9b81199fac805210 -->

# Triggering a Contract Negotiation

Contract negotiation initiation between a data consumer and provider. Use this process to formally request and agree upon conditions for consuming data from a provider's catalog offer.



## Prerequisites

You've discovered the provider's catalog and selected an offer that's right for you. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).



## Context

Once you've selected an offer from a catalog, you can start the contract negotiation with the provider.



## Procedure

1.  After selecting an offer that you want to consume from the catalog's response, initiate the negotiation with the following POST call:

    > ### Code Syntax:  
    > ```
    > /api/dsi/v1/contract-negotiation
    > ```

2.  In the request body, provide the following information:


    <table>
    <tr>
    <th valign="top">

    Variable
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `counterPartyAddress` 
    
    </td>
    <td valign="top">
    
    Find it through the discovery of the data space that you're a participant of.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `counterPartyId` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `offerId` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `permissions`
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `assetId` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    </table>
    
    The following is an example of the request body:

    > ### Sample Code:  
    > ```
    > {
    >   "name": "My Negotiation",
    >   "counterPartyAddress": "https://provider.example.com/api/v1/dsp",
    >   "counterPartyId": "BPNL000000000001",
    >   "offerId": "offer-xyz789",
    >   "permissions": [
    >     {
    >             "operandLeft": "UsagePurpose",
    >             "operator": "eq",
    >             "operandRight": "cx.quality.base:1"
    >         },
    >         {
    >             "operandLeft": "FrameworkAgreement",
    >             "operator": "eq",
    >             "operandRight": "DataExchangeGovernanceCredential:1.0"
    >      }
    >   ],
    >   "assetId": "asset-01"
    > }
    > ```

    As a response to this contract negotiation call, you get the **contract negotiation ID**.

3.  The negotiation can then take some time since the communication and negotiation happen asynchronously. Regularly check the state of your contract negotiation using the following GET call:

    > ### Code Syntax:  
    > ```
    > /api/dsi/v1/contract-negotiation/{id}/state
    > ```

    Once the negotiation reaches the status **FINALIZED**, you can continue.

4.  With the provider having accepted the negotiation, both provider and consumer agree on the conditions. Get the final **contract agreement ID** using the following GET call:

    > ### Code Syntax:  
    > ```
    > /api/dsi/v1/contract-negotiation/{id}/agreement
    > ```




## Next Steps

Next, you use the agreement ID to trigger the transfer process for your desired asset.

Depending on your use case, continue with one of the following procedures:

-   [Consuming Assets Into S3 Storage](consuming-assets-into-s3-storage-4afdf5c.md)
-   [Consuming Assets Into Azure Blob Storage](consuming-assets-into-azure-blob-storage-0088840.md)
-   [Consuming HTTP Assets](consuming-http-assets-f6b27ac.md)

