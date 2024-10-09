<!-- loioeace95e9ecb44768a8d2010f79573541 -->

# Triggering Contract Negotiations and Transferring Assets with EDR Management APIs

To consume assets, you must agree with the provider on the conditions. This process happens in a contract negotiation, after which you can transfer your assets.



<a name="loioeace95e9ecb44768a8d2010f79573541__prereq_lvb_njd_2zb"/>

## Prerequisites

-   You've completed the steps described in [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md), in which you successfully discovered assets in the catalog.
-   The role collection `DataspaceConsumer` and the role `credentialWrite` are assigned to your user.

> ### Caution:  
> If your business partner wants to consume your assets using the EDR Management APIs, they must use Data Space Integration, too. If they use a different Eclipse Dataspace Connector, they can't consume the asset. Instead, they must follow the alternative negotiation process described in [Consuming S3 Assets](consuming-s3-assets-4afdf5c.md).



## Context

This topic describes the recommended process for triggering a contract negotiation and transferring HTTP assets using EDR \(Endpoint Data Reference\) Management APIs. We recommend this option for frequently used assets, however, it also creates a lot of traffic.

If you want to work with S3 assets, see [Consuming S3 Assets](consuming-s3-assets-4afdf5c.md).

> ### Note:  
> When you use EDR Management APIs, EDRs are stored. Once they're about to expire, the Transfer Process is triggered automatically to get a fresh EDR token. This ultimately results in more traffic between the provider and the consumer. Therefore, consider the following before using this method:
> 
> -   To avoid unnecessary traffic, we recommend only using this API for assets that are frequently used.
> 
> -   Always check for your given assets whether the transfer process has already started before initiating another request \(see Step 4\). This avoids duplicate effort, meaning less traffic, and less load.
> 
> -   Delete EDR tokens if you do no need them anymore to reduce traffic \(see Step 6\).



## Procedure

1.  Start the transfer process with a single request for the contract negotiation and the transfer process:

    > ### Sample Code:  
    > ```
    > POST /api/management/v2/edrs
    > 								
    > 								{
    > 								"@context": [
    > 								"https://w3id.org/tractusx/policy/v1.0.0",
    > 								{
    > 								"@vocab": "https://w3id.org/edc/v0.0.1/ns/"
    > 								}
    > 								],
    > 								"@type": "ContractRequest",
    > 								"counterPartyAddress": "{{providerControlPlaneDsp}}",
    > 								"counterPartyId": "{{providerBPN}}",
    > 								"protocol": "dataspace-protocol-http",
    > 								"policy": {
    > 								"@context": "http://www.w3.org/ns/odrl.jsonld",
    > 								"@type": "Offer",
    > 								"@id": "{{offerId}}",
    > 								"assigner": "{{providerBPN}}",
    > 								"target": "{{assetId}}",
    > 								"permission": "{{permission}}",
    > 								"prohibition": [],
    > 								"obligation": []
    > 								}
    > 								}
    > ```

    The response includes the `ContractNegotiationId`.

2.  Use the following API to request the state of the contract negotiation:

    > ### Sample Code:  
    > ```
    > GET /api/management/v3/contractnegotiations/{{negotiationId}}/state
    > ```

3.  Once the contract negotiation has reached the state **FINALIZED**, the contract agreement can be retrieved by using the following call:

    > ### Sample Code:  
    > ```
    > GET /api/management/v3/contractnegotiations/{{negotiationId}}/agreement
    > ```

4.  To retrieve the cached EDRs, first get the Transfer Process Id.

    > ### Sample Code:  
    > ```
    > GET /api/management/v3/edrs?assetId={{assetId}}&agreementId={{agreementId}}
    > ```

    The API returns both the `assetId` and the `agreementId`, or each of them individually. If you return a combination of both, you ensure a single `transferProcessId`. If only one is provided, this can result in an array of transfer process details.

    This is the response for a single EDR:

    > ### Sample Code:  
    > ```
    > [
    > 								{
    > 								"@type": "tx:EndpointDataReferenceEntry",
    > 								"edc:agreementId": "<<contract-agreement-id>>",
    > 								"edc:transferProcessId": "<<transfer-process-id>>",
    > 								"edc:assetId": "<<asset-id>>",
    > 								"edc:providerId": "<<providerBPN>>",
    > 								"tx:edrState": "NEGOTIATED",
    > 								"tx:expirationDate": 1704908278000,
    > 								"@context": {
    > 								"dct": "https://purl.org/dc/terms/",
    > 								"tx": "https://w3id.org/tractusx/v0.0.1/ns/",
    > 								"edc": "https://w3id.org/edc/v0.0.1/ns/",
    > 								"dcat": "https://www.w3.org/ns/dcat/",
    > 								"odrl": "http://www.w3.org/ns/odrl/2/",
    > 								"dspace": "https://w3id.org/dspace/v0.8/"
    > 								}
    > 								}
    > 								]
    > ```

    This is the response for multiple EDRs \(when either the assetId or agreementId is given, and when there are multiple transferProcess combinations\):

    > ### Sample Code:  
    > ```
    > [
    > 								{
    > 								"@type": "tx:EndpointDataReferenceEntry",
    > 								"edc:agreementId": "<<contract-agreement-id1>>",
    > 								"edc:transferProcessId": "<<transfer-process-id1>>",
    > 								"edc:assetId": "<<asset-id>>",
    > 								"edc:providerId": "<<providerBPN>>",
    > 								"tx:edrState": "NEGOTIATED",
    > 								"tx:expirationDate": 1704908278000,
    > 								"@context": {
    > 								"dct": "https://purl.org/dc/terms/",
    > 								"tx": "https://w3id.org/tractusx/v0.0.1/ns/",
    > 								"edc": "https://w3id.org/edc/v0.0.1/ns/",
    > 								"dcat": "https://www.w3.org/ns/dcat/",
    > 								"odrl": "http://www.w3.org/ns/odrl/2/",
    > 								"dspace": "https://w3id.org/dspace/v0.8/"
    > 								}
    > 								},
    > 								{
    > 								"@type": "tx:EndpointDataReferenceEntry",
    > 								"edc:agreementId": "<<contract-agreement-id2>>",
    > 								"edc:transferProcessId": "<<transfer-process-id2>>",
    > 								"edc:assetId": "<<asset-id>>",
    > 								"edc:providerId": "<<providerBPN>>",
    > 								"tx:edrState": "NEGOTIATED",
    > 								"tx:expirationDate": 1704808278000,
    > 								"@context": {
    > 								"dct": "https://purl.org/dc/terms/",
    > 								"tx": "https://w3id.org/tractusx/v0.0.1/ns/",
    > 								"edc": "https://w3id.org/edc/v0.0.1/ns/",
    > 								"dcat": "https://www.w3.org/ns/dcat/",
    > 								"odrl": "http://www.w3.org/ns/odrl/2/",
    > 								"dspace": "https://w3id.org/dspace/v0.8/"
    > 								}
    > 								}
    > 								]
    > ```

5.  To get the EDR details, add the transferProcessId from the response to the following call:

    > ### Sample Code:  
    > ```
    > GET /api/management/v2/edrs/{{transferprocessId}}
    > ```

    > ### Sample Code:  
    > ```
    > {
    > 								"@type": "edc:DataAddress",
    > 								"edc:cid": "<<contract-agreement-id>>",
    > 								"edc:type": "EDR",
    > 								"edc:authCode": "<<Bearer Authorization token>>",
    > 								"edc:endpoint": "<<dataplane endpoint url>>>>",
    > 								"edc:id": "<<Id>>",
    > 								"edc:authKey": "Authorization",
    > 								"@context": {
    > 								"dct": "https://purl.org/dc/terms/",
    > 								"tx": "https://w3id.org/tractusx/v0.0.1/ns/",
    > 								"edc": "https://w3id.org/edc/v0.0.1/ns/",
    > 								"dcat": "https://www.w3.org/ns/dcat/",
    > 								"odrl": "http://www.w3.org/ns/odrl/2/",
    > 								"dspace": "https://w3id.org/dspace/v0.8/"
    > 								}
    > 								}
    > ```

    With the response details, you can make a call to the data plane provider and to get all of the asset's details.

6.  The stored EDR's token has an expiration time of 70 mins.

    Around 60 seconds before the token expires, the `transferProcess` is initiated again to get a new fresh EDR token. Once successfully executed, the new `transferProcessId expirationTime` token gets updated in the database vault automatically. Expired token and EDR details are removed.

    For the automatic refresh of the EDRS token, perform the following call:

    ```
    GET /api/management/v2/edrs/"transferprocessId"/dataaddress?auto_refresh=true
    ```

    If you want to refresh the EDR manually, perform the call:

    ```
    POST/api/management/v2/edrs/"transferprocessId"/refresh
    ```

    When you don't require an EDR anymore, you need to delete it using the API. This way, you avoid unnecessary traffic between the consumer and the provider. Use the following call:

    > ### Sample Code:  
    > ```
    > DELETE /api/management/v2/edrs/{{transferprocessId}}
    > ```




<a name="loioeace95e9ecb44768a8d2010f79573541__postreq_dmz_pjd_2zb"/>

## Next Steps

Having successfully closed the contract negotiation and received the contract agreement ID, you can now start the transfer process to consume your assets. See [Consuming Assets](consuming-assets-f6b27ac.md).

