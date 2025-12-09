<!-- loio008884076c3346df94fd0bc67fa0b7d8 -->

# Consuming Assets Into Azure Blob Storage

Learn how to trigger a contract negotiation, agree with a provider on the conditions for using their assets, and transfer assets to your desired location.



<a name="loio008884076c3346df94fd0bc67fa0b7d8__prereq_zjj_x1d_2zb"/>

## Prerequisites

You've completed the steps described in [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md), in which you discovered the provider's catalog and selected an offer that's right for you.



## Context

This topic describes the recommended process to trigger a contract negotiation and transfer both S3 and Azure assets to your Azure Blob Storage. For the process of transferring assets to your Amazon S3 storage, see [Consuming S3 and Azure Assets](consuming-s3-and-azure-assets-4afdf5c.md). For HTTP assets, see [Consuming HTTP Assets](consuming-http-assets-735300c.md).



## Procedure

1.  After selecting an offer that you want to consume from the catalog's response, initiate the negotiation with the following POST call:

    > ### Code Syntax:  
    > ```
    > <managementURL>/api/management/v3/contractnegotiations
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
    
    `edc:connectorAddress` \(provider URL\)
    
    </td>
    <td valign="top">
    
    Find it through the discovery of the data space that you're a participant of.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `edc:providerID` and `edc:connectorID` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `edc:offerID` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `edc:assetID` 
    
    </td>
    <td valign="top">
    
    Find it in the offer that you want to consume. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `edc:permission`
    
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
    > "@context": {
    >             "@vocab": "https://w3id.org/edc/v0.0.1/ns/",
    >             "edc": "https://w3id.org/edc/v0.0.1/ns/",
    >             "odrl": "http://www.w3.org/ns/odrl/2/"
    >     },
    >     "@type": "edc:ContractRequest",
    >     "edc:counterPartyAddress": "{{providerUrl}}",
    >     "edc:counterPartyId": "{{providerBPN}}",
    >     "edc:protocol": "dataspace-protocol-http",
    >     "edc:policy": {
    >         "@type": "odrl:Offer",
    >         "@id": "{{offerId}}",
    >         "odrl:assigner": {
    >             "@type": "odrl:Assigner",
    >             "@id": "{{providerBPN}}"
    >         },
    >         "odrl:target": {
    >             "@type": "odrl:Target",
    >             "@id": "{{assetId}}"
    >         },
    >         "odrl:permission": "{{permission}}",
    >         "odrl:prohibition": [],
    >         "odrl:obligation": []
    >     }
    > }
    > ```

3.  As a response of this contract negotiation call, you get the contract negotiation ID.

    This process can take some time. This communication and negotiation is an asynchronous process, so come back to regularly check the status of the negotiation. You can use two different calls to check the status of your negotiation:

    You can query the state of your contract negotiation using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationId}}/state
    > ```

    Alternatively, you can query information about the contract negotiation and its status using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationid}}
    > ```

    The response then includes the fields `edc:state`.

    The negotiation state must be **FINALIZED** to perform the transfer process.

4.  Once the negotiation reached **FINALIZED**, you receive a contract agreement ID, which you need in the next step. You can get the contract agreement ID by using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationId}/agreement
    > ```

5.  Having received your contract agreement ID, you can now transfer the assets to your Azure Blob Storage. To do that, you must decide how to grant access to your Azure account details when triggering the transfer process: You can either create a token yourself and store it under an alias, which you then refer to, or upload your credentials as a token. Both options use the [token API](https://hub.sap.com/api/DSIAPI/resource/Credentials_Alias) and are described in the following.

    To create credentials in Data Space Integration, you need the role `CredentialsWrite`. This role is included in the role collection `DataspaceTechnicalAdmin`, but you can also assign the role to your user individually in the SAP BTP cockpit.

    -   **Option 1: Create SAS Token and Alias Yourself**

        1.  Create the SAS token from your user delegation key, as described in [Create a user delegation SAS](https://learn.microsoft.com/en-us/rest/api/storageservices/create-user-delegation-sas). It must have the required permissions to perform the transfer.

        2.  Use the API call [Generate STS Alias](https://int.api.hana.ondemand.com/api/DSIAPI/path/generateAlias) to store the token secret and define the alias as follows:

            ```
            POST {{consumerControlPlaneDsi}}/api/v1/dsi/credentials/token
            Content-Type: application/json
            
            {
                "alias": "{{aliasName}}",
                "credentials": {
                   "sas":"{{sas-token}}"
                }
            }
            ```

        3.  In step 6, enter the SAS token alias as `keyName` in the payload for triggering the transfer process.


    -   **Option 2: Let Data Space Integration Create Token Based on Your Account Credentials**

        Your credentials alias must follow the pattern `accountName-key1`, with `accountName` being your Azure account name. Data Space Integration uses your credentials in the transfer process. Therefore, you don't need to provide any account details in the payload in the next step.

        The API call looks as follows:

        ```
        POST {{consumerControlPlaneDsi}}/api/v1/dsi/credentials/token
        
        {
          "alias": "{{accountName}}-key1",
          "credentials": {
            "azureKey": ""
          }
        }
        ```

        > ### Caution:  
        > Make sure that the credentials are valid for the account. Since the credentials are cached in the control plane, it must be restarted to reflect any changes you make. In this case, please get in touch with support. See [Troubleshooting for Data Space Integration](troubleshooting-for-data-space-integration-166fa88.md).


6.  Next, trigger the transfer process using the following payload. Make sure that the container that you enter exists since otherwise Data Space Integration runs into an error. For more details, refer to the [transfer process API](https://int.api.hana.ondemand.com/api/DSIAPI/resource/Transfer_Process) and select an example for Azure.

    > ### Note:  
    > While the Eclipse Dataspace Connector supports the use of `blobName` in the data destination, Data Space Integration doesn't support this parameter. Only use the parameters used in the following example payload.

    ```
    {
       "@context": {
           "@vocab": "https://w3id.org/edc/v0.0.1/ns/",
           "edc": "https://w3id.org/edc/v0.0.1/ns/"
       },
       "@type": "edc:TransferRequest",
       "edc:protocol": "dataspace-protocol-http",
       "edc:counterPartyAddress": "{{providerControlPlaneDsp}}",
       "edc:contractId": "{{agreementId}}",
       "edc:assetId": "{{assetId}},
       "edc:transferType": "AzureStorage-PUSH",
       "edc:dataDestination": {
           "type": "AzureStorage",
           "account": "{{consumerAccount}}",
           "container": "{{consumerContainer}}"
           "keyName": "{{azure-sas-alias}}", / use only if you create an alias yourself
           "folderName": "destinationFolder/", / optional 
       },
       "edc:privateProperties": {
           "private-key": "private-value"
       }
    }
    ```

7.  Once you've triggered the transfer process, you can check its status with the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/transferprocesses/{id}/state
    > ```

    Once the status reaches *successful*, you can find the asset in the bucket you defined in the transfer process payload.




<a name="loio008884076c3346df94fd0bc67fa0b7d8__result_sb4_qjz_pcc"/>

## Results

You've successfully closed a contract negotiation, received the contract agreement ID, and the provider transferred an asset into your bucket.

