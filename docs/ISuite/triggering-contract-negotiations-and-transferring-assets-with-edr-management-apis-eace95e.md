<!-- loioeace95e9ecb44768a8d2010f79573541 -->

# Triggering Contract Negotiations and Transferring Assets with EDR Management APIs

To consume assets, you must agree with the provider on the conditions. This process happens in a contract negotiation, after which you can transfer your assets.



<a name="loioeace95e9ecb44768a8d2010f79573541__prereq_lvb_njd_2zb"/>

## Prerequisites

-   You've completed the steps described in [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md), in which you successfully discovered assets in the catalog.
-   The role collection `DataspaceConsumer` and the role `credentialWrite` are assigned to your user.



## Context

This topic describes the recommended process for triggering a contract negotiation and transferring HTTP assets using EDR \(Endpoint Data Reference\) Management APIs. We recommend this option for frequently used assets, however, it also creates a lot of traffic.

If you want to work with S3 assets, see [Consuming S3 and Azure Assets](consuming-s3-and-azure-assets-4afdf5c.md).



## Procedure

1.  Start the transfer process with a single request for the contract negotiation and the transfer process:

    > ### Sample Code:  
    > ```
    > POST /api/management/v2/edrs
    > 								
    > {
    >     "@context": {
    >       "@vocab": "https://w3id.org/edc/v0.0.1/ns/",
    >       "edc": "https://w3id.org/edc/v0.0.1/ns/",
    >       "odrl": "http://www.w3.org/ns/odrl/2/",
    >       "cx-policy": "https://w3id.org/catenax/policy/"
    >     },   
    >     "@type": "edc:ContractRequest",
    >     "edc:counterPartyAddress": "{{providerControlPlaneDsp}}",
    >     "edc:counterPartyId": "{{providerBPN}}",
    >     "edc:protocol": "dataspace-protocol-http",
    >     "edc:policy": {       
    >         "@type": "odrl:Offer",
    >         "@id": "{{offerId}}",
    >         "odrl:assigner": "{{providerBPN}}",
    >         "odrl:target": "{{assetId}}",
    >         "odrl:permission": "{{permission}}",
    >         "odrl:prohibition": [],
    >         "odrl:obligation": []
    >     }
    > }					
    > ```

    The response includes the `ContractNegotiationId`.

2.  Optionally, you can use the following API to request the state of the contract negotiation:

    > ### Sample Code:  
    > ```
    > GET /api/management/v3/contractnegotiations/{{negotiationId}}/state
    > ```

3.  Optionally, once the contract negotiation has reached the state **FINALIZED**, you can retrieve it by using the following call:

    > ### Sample Code:  
    > ```
    > GET /api/management/v3/contractnegotiations/{{negotiationId}}/agreement
    > ```

4.  To retrieve the cached EDRs, perform one of the following calls. You can use an asset query, an agreement query, or a negotiation query.

    -   Asset query:

        ```
        POST/api/management/v2/edrs/request
        
        {
            "@context": {
                "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
            },
            "@type": "edc:QuerySpec",
            "edc:filterExpression": {
                "@type": "edc:Criterion",
                "edc:operandLeft": "assetId",
                "edc:operator": "=",
                "edc:operandRight": "{{assetId}}"
            },
            "edc:sortOrder": "ASC",
            "edc:offset": 0,
            "edc:limit": 100
        }
        ```

    -   Agreement query:

        ```
        POST /api/management/v2/edrs/request 
        
        {
            "@context": {
                "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
            },
            "@type": "edc:QuerySpec",
            "edc:filterExpression": {
                "@type": "edc:Criterion",
                "edc:operandLeft": "agreementId",
                "edc:operator": "=",
                "edc:operandRight": "{{agreementId}}"
            },
            "edc:sortOrder": "ASC",
            "edc:offset": 0,
            "edc:limit": 100
        }
        ```

    -   Negotiation query:

        ```
        POST /api/management/v2/edrs/request
        
        {
            "@context": {
                "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
            },
            "@type": "edc:QuerySpec",
            "edc:filterExpression": {
                "@type": "edc:Criterion",
                "edc:operandLeft": "contractNegotiationId",
                "edc:operator": "=",
                "edc:operandRight": "{{negotiationId}}"
            },
            "edc:sortOrder": "ASC",
            "edc:offset": 0,
            "edc:limit": 100
        }
        ```


5.  After performing one of the API calls from the previous step, you can now get the EDR details by performing the following call and adding the transfer process ID:

    > ### Sample Code:  
    > ```
    > GET/api/management/v2/edrs/{{transferprocessId}}/dataaddress
    > ```

    With the response details, you can call the data plane provider and to get the asset's details.

6.  The stored EDR's token has an expiration time of 70 mins.

    Around 60 seconds before the token expires, the `transferProcess` is initiated again to get a new fresh EDR token. Once successfully executed, the new `transferProcessId expirationTime` token gets updated in the database vault automatically. Expired token and EDR details are removed.

    For the automatic refresh of the EDRS token, perform the following call:

    ```
    GET /api/management/v2/edrs/{{transferprocessId}}/dataaddress?auto_refresh=true
    ```

    If you want to refresh the EDR manually, perform the call:

    ```
    POST/api/management/v2/edrs/{{transferprocessId}}/refresh
    ```

    When you don't require an EDR anymore, you need to delete it using the API. This way, you avoid unnecessary traffic between the consumer and the provider. Use the following call:

    > ### Sample Code:  
    > ```
    > DELETE /api/management/v2/edrs/{{transferprocessId}}
    > ```




<a name="loioeace95e9ecb44768a8d2010f79573541__postreq_dmz_pjd_2zb"/>

## Next Steps

Having successfully closed the contract negotiation and received the contract agreement ID, you can now start the transfer process to consume your assets. See [Consuming Assets](consuming-assets-f6b27ac.md).

