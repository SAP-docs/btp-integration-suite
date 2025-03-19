<!-- loio90f36199e0bc4bd9956fb69312fbc2ab -->

# Discovering Offers Through a Catalog

Before you can consume an asset of another data space participant, you must discover their catalog and decide on an offer.



<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__prereq_spz_3kd_2zb"/>

## Prerequisites

-   You know the `provider URL`, which is the external connector address of the other data space participants from whom you want to consume the asset. See: [Catena-X](https://catena-x.net/en/).

-   You have a valid OAuth2 access token. You can retrieve the necessary details from the service key.

-   Some calls require a `managementURL`, which you can retrieve from the service key.

-   You have the following consumer-related roles/role collection. With the `DataspaceConsumer` role collection, all consumer operations can be performed. If you don't have that role collection, you need roles dedicated for each operation:


    <table>
    <tr>
    <th valign="top">

    Operation
    
    </th>
    <th valign="top">

    Role
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Query Catalog
    
    </td>
    <td valign="top">
    
    `Catalog.Read`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Contract Negotiation
    
    </td>
    <td valign="top">
    
    `ContractNegotiation.Read`

    `ContractNegotiation.Write`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Contract Agreement
    
    </td>
    <td valign="top">
    
    `ContractAgreement.Read` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transfer Process
    
    </td>
    <td valign="top">
    
    `TransferProcess.Read`

    `TransferProcess.Write`
    
    </td>
    </tr>
    </table>
    



## Context

To successfully reach a contract agreement using the consumer APIs, as a consumer, prepare the following steps:

You initiate a negotiation by contacting your partner/a provider. Once you've found the assets that you want to consume, you need to initiate a contract negotiation, that is, the process in which you and the provider agree on the conditions based on which you can consume the assets. To do so, use the API provided in the [SAP Business Accelerator Hub](https://api.sap.com/package/dataspaceintegration/rest).



<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__steps_r2y_bcx_dzb"/>

## Procedure

1.  Request the catalog content containing a list of all offers available with the following POST call. Note that you must insert your specific `managementURL`.

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/catalog/request
    > ```

    Provide the following request body with the following information. Use filters as needed and pay attention to `offset` and `limit`. Have a look at the sample code and replace the placeholder values. The provider URL is accessible via Catena-X.

    > ### Sample Code:  
    > ```
    > {
    >   "@context": {
    >     "edc": "https://w3id.org/edc/v0.0.1/ns/",
    >     "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
    >   },
    >   "@type": "CatalogRequest",
    >   "edc:protocol": "dataspace-protocol-http",
    >   "edc:counterPartyAddress": "<providerURL of your business partner>",
    >   "edc:counterPartyId": "<providerBPN of your business partener>",
    >   "edc:querySpec": {
    >     "@type":"QuerySpec",
    >     "edc:sortOrder": "ASC",     
    >     "edc:offset": 0,
    >     "edc:limit": 100        
    >   }
    > }
    > ```

2.  As a result, you receive the catalog of the specific connector that you asked for. Under `dcat:dataset` in the response, you can find all the offers registered on this connector. Remember that an offer consists of assets and policies.

    Have a look at the following example:

    > ### Sample Code:  
    > ```
    > {
    >     "@id": "",
    >     "@type": "dcat:Catalog",
    >     "dspace:participantId": "",
    >     "dcat:dataset": {
    >         "@id": "",
    >         "@type": "dcat:Dataset",
    >         "odrl:hasPolicy": {
    >             "@id": "",
    >             "@type": "odrl:Offer",
    >             "odrl:permission": {
    >                 "odrl:action": {
    >                     "@id": "odrl:use"
    >                 }
    >             },
    >             "odrl:prohibition": [],
    >             "odrl:obligation": []
    >         },
    >         "dcat:distribution": [
    >             {
    >                 "@type": "dcat:Distribution",
    >                 "dct:format": {
    >                     "@id": "HttpData-PULL-PUSH"
    >                 },
    >                 "dcat:accessService": {
    >                     "@id": "",
    >                     "@type": "dcat:DataService",
    >                     "dcat:endpointDescription": "dspace:connector",
    >                     "dcat:endpointUrl": "",
    >                     "dct:terms": "dspace:connector",
    >                     "dct:endpointUrl": ""
    >                 }
    >             },
    >             {
    >                 "@type": "dcat:Distribution",
    >                 "dct:format": {
    >                     "@id": "HttpData-PULL"
    >                 },
    >                 "dcat:accessService": {
    >                     "@id": "",
    >                     "@type": "dcat:DataService",
    >                     "dcat:endpointDescription": "dspace:connector",
    >                     "dcat:endpointUrl": "",
    >                     "dct:terms": "dspace:connector",
    >                     "dct:endpointUrl": ""
    >                 }
    >             }
    >         ],
    >         "version": "0.7.1",
    >         "additionalDescription": "DSI Demo Asset",
    >         "name": "DSI-Demo-Asset - 211",
    >         "description": "Asset for demonstration purpose",
    >         "id": ""
    >     },
    >     "dcat:service": {
    >         "@id": "",
    >         "@type": "dcat:DataService",
    >         "dcat:endpointDescription": "dspace:connector",
    >         "dcat:endpointUrl": "",
    >         "dct:terms": "dspace:connector",
    >         "dct:endpointUrl": ""
    >     },
    >     "participantId": "",
    >     "@context": {
    >         "@vocab": "https://w3id.org/edc/v0.0.1/ns/",
    >         "edc": "https://w3id.org/edc/v0.0.1/ns/",
    >         "tx": "https://w3id.org/tractusx/v0.0.1/ns/",
    >         "tx-auth": "https://w3id.org/tractusx/auth/",
    >         "cx-policy": "https://w3id.org/catenax/policy/",
    >         "dcat": "http://www.w3.org/ns/dcat#",
    >         "dct": "http://purl.org/dc/terms/",
    >         "odrl": "http://www.w3.org/ns/odrl/2/",
    >         "dspace": "https://w3id.org/dspace/v0.8/"
    >     }
    > }
    > ```

3.  Once you've gone through all the available offers, choose the one that you want to consume. Note down the `offer ID (ID under hasPolicy)`, `asset ID (ID field in dcat:dataset)`, `provider ID (participant ID)`, and the contents of `odrl:permission` as you'll need them to trigger the contract negotiation in the next steps.




<a name="loio90f36199e0bc4bd9956fb69312fbc2ab__postreq_hcc_rjd_2zb"/>

## Next Steps

Now that you've decided on an offer, you can start a contract negotiation with the provider. Depending on the type of asset you're working with, continue with one of the following:

-   [Consuming S3 and Azure Assets](consuming-s3-and-azure-assets-4afdf5c.md)

-   [Consuming HTTP Assets](consuming-http-assets-735300c.md)


.

