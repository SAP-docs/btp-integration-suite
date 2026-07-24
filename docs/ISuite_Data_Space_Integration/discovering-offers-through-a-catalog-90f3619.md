<!-- loio90f36199e0bc4bd9956fb69312fbc2ab -->

# Discovering Offers Through a Catalog

Before you can consume an asset of another data space participant, you must discover their catalog and decide on an offer.



<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__prereq_spz_3kd_2zb"/>

## Prerequisites

-   You know the `provider URL`, which is the external connector address of the other data space participants from whom you want to consume the asset.

-   You have a valid OAuth2 access token with the corresponding authorizations for consumer operations, for example, `DataspaceConsumer`. You can retrieve the credentials from the service key.




## Context

The discovery of a provider's catalog is the first step to consuming an asset.



<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__steps_r2y_bcx_dzb"/>

## Procedure

1.  Request the catalog content containing a list of all offers available with the following POST call.

    > ### Code Syntax:  
    > ```
    > /api/dsi/v1/catalog
    > ```

    Provide the following request body with the following information. Have a look at the sample code and replace the example values with your specific value. The counter party address can be found in the discovery service of the data space, for example, Cofinity-X Beta Jupiter.

    > ### Sample Code:  
    > ```
    > {
    >   "counterPartyAddress": "https://provider.example.com/api/v1/dsp",
    >   "counterPartyId": "BPNL000000000001",
    >   "filterExpression": [
    >     {
    >       "operandLeft": "properties.'http://purl.org/dc/terms/type'.'@id'",
    >       "operator": "EQ",
    >       "operandRight": "my-asset-01"
    >     }
    >   ]
    > }
    > ```

2.  As a result, you receive the catalog response of the specific connector that you requested in your query. In the response, you can find all the offers registered on this connector that fit your filter criteria. Remember that an offer consists of assets and policies.

    Have a look at the following example:

    > ### Sample Code:  
    > ```
    > {
    >     "counterpartyId": "BPNL000000011EOO",
    >     "dataset": [
    >         {
    >             "assetId": "Asset-1",
    >             "endpoint": "https://provider-sdx-dsi2-0-temp-3l334y15.acfun001.dsi.integration.dev-canary.cloud.sap/api/v1/dsp",
    >             "transferType": [
    >                 "HttpData-PULL"
    >             ],
    >             "policy": [
    >                 {
    >                     "offerId": "Q29udHJhY3QtRGVmaW5pdGlvbi0x:QXNzZXQtMQ==:OTIzODE1ZjYtZDU4ZC00YzRmLWFiNDgtNjJiY2I4N2ZlZmY4",
    >                     "permissions": [
    >                         {
    >                             "operandLeft": "ContractReference",
    >                             "operator": "isAllOf",
    >                             "operandRight": [
    >                                 "contract123"
    >                             ]
    >                         },
    >                         {
    >                             "operandLeft": "FrameworkAgreement",
    >                             "operator": "eq",
    >                             "operandRight": "DataExchangeGovernance:1.0"
    >                         },
    >                         {
    >                             "operandLeft": "UsagePurpose",
    >                             "operator": "isAnyOf",
    >                             "operandRight": [
    >                                 "cx.core.industrycore:1",
    >                                 "cx.core.qualityNotifications:1",
    >                                 "cx.pcf.base:1"
    >                             ]
    >                         }
    >                     ],
    >                     "prohibitions": [],
    >                     "obligations": [],
    >                     "extensibleProperties": {}
    >                 }
    >             ],
    >             "demoProp": "helloWorld"
    >         }
    >     ]
    > }
    > ```

3.  Once you've gone through all the available offers, choose the one that you want to consume. Note down the `offer ID`, `asset ID`, `counter party ID (provider ID)`, and the contents of `permissions` as you'll need them to trigger the contract negotiation in the next steps.




<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__postreq_hcc_rjd_2zb"/>

## Next Steps

Now that you've decided on an offer, you can start a contract negotiation with the provider. See [Triggering a Contract Negotiation](triggering-a-contract-negotiation-dc11922.md).

