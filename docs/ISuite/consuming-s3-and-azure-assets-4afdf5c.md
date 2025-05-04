<!-- loio4afdf5c06302482fb2fff87ed94f3896 -->

# Consuming S3 and Azure Assets

Learn how to trigger a contract negotiation, agree with a provider on the conditions for using their assets, and transfer assets to your desired location.



<a name="loio4afdf5c06302482fb2fff87ed94f3896__prereq_zjj_x1d_2zb"/>

## Prerequisites

You've completed the steps described in [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md), in which you discovered the provider's catalog and selected an offer that's right for you.



## Context

This topic describes the recommended process to trigger a contract negotiation and transfer Amazon S3 assets and Azure assets. For the process for HTTP assets, see [Consuming HTTP Assets](consuming-http-assets-735300c.md).



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

    This process can take some time. This communication and negotiation is an asynchronous process, so come back to regularly check the status of the negotiation. The negotiation state must be **FINALIZED** to perform the transfer process. You can use two different calls to check the status of your negotiation:

    You can query the state of your contract negotiation using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationId}}/state
    > ```

    The negotiation state must be **FINALIZED** to perform the transfer process.

    Alternatively, you can query information about the contract negotiation and its status using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationid}}
    > ```

    The response then includes the fields `edc:state` and `edc:contractAgreementId`.

4.  Once the provider has accepted the negotiation, and both provider and consumer agree on the conditions, you receive a contract agreement ID. You can get the contract agreement ID by using the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/contractnegotiations/{{negotiationId}/agreement
    > ```

5.  You can now transfer your assets.

    If you want to consume **Azure** assets, skip this step and continue with step 6.

    For **S3** assets, your request must include a data destination, which is the location to which the provider transfers the asset.

    You have two options for using credentials in your call: you can either enter a **permanent access key ID and access key secret** directly into the payload, or you can generate an **alias** beforehand using the AWS Secret Token Service \(STS\) and then refer to it in the payload.

    -   If you're using a **permanent access key ID and access key secret**, start the transfer process with the following POST call and body.

        > ### Remember:  
        > Make sure to assign the permission to delete roles to your Amazon S3 user. Since Data Space Integration temporarily shares the access with the provider, the permission allows Data Space Integration to remove the access again after the exchange.

        > ### Sample Code:  
        > ```
        > POST /api/management/v3/transferprocesses
        > 									
        > {
        >     "@context": [
        >         {
        >             "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
        >         },
        >         {
        >             "edc": "https://w3id.org/edc/v0.0.1/ns/"
        >         }
        >     ],
        >     "@type": "edc:TransferRequest",
        >     "edc:protocol": "dataspace-protocol-http",
        >     "edc:counterPartyAddress": "{{providerControlPlaneDsp}}",
        >     "edc:contractId": "{{agreementId}}",
        >     "edc:assetId": "{{assetId}}",
        >     "edc:transferType": "AmazonS3-PUSH",
        >     "edc:dataDestination": {
        >         "edc:type": "AmazonS3",
        >         "edc:bucketName": "",
        >         "edc:region": "eu-central-1",
        >         "edc:folderName": "testConsumerFolder",
        >         "edc:objectName": "testfilename_10mb.txt",
        >         "edc:accessKeyId": "{{transferprocessS3AccessKeyId}}",
        >         "edc:secretAccessKey": "{{transferprocessS3SecretAccessKey}}"
        >     },
        >     "edc:privateProperties": {
        >         "private-key": "private-value"
        >     }
        > }			
        > ```

    -   As an alternative to using the permanent accessKeyId and secretAccessKey, you can also create an **alias** instead, using temporary security credentials created with the AWS Secure Token Service \(STS\). After you've generated STS credentials, use these temporary credentials to receive an alias, and use this alias when initiating a transfer for S3 assets as a consumer.

        > ### Note:  
        > To upload the token in Data Space Integration, you need the role `CredentialsWrite`. This role is included in the role collection `DataspaceTechnicalAdmin`, but you can also assign the role to your user individually in the SAP BTP cockpit.

        To use an STS alias, perform the following steps:

        1.  Generate STS credentials using the AWS command-line interface. For instructions and more information, see [Temporary security credentials in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html), [Request temporary security credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html) and [AWS STS examples using AWS CLI](https://docs.aws.amazon.com/cli/v1/userguide/cli_sts_code_examples.html)in the AWS documentation.

            The credentials consist of the following fields, which you'll need to enter in the next step:

            -   `accessKeyId`: A temporary access key ID that was generated by AWS

            -   `secretAccessKey`: A temporary secret access key that was generated by AWS

            -   `sessionToken`: A token used to validate your temporary security credentials

            -   `expiration`: Once your temporary security credentials have expired, you must generate new credentials.


        2.  To store your credentials in the vault of Data Space Integration, perform the following API call:

            ```
            POST /api/v1/dsi/credentials/token																		{
              "alias": "{{aliasName}}",
              "credentials": {
              "accessKeyId": "{{awsTemporaryAccessKeyId}}",
              "secretAccessKey": "{{awsTemporarySecretAccessKey}}",
              "sessionToken": "{{sessionToken}}",
              "expiration": "{{expiration}}"
            }
            }
            ```

            You can either enter your own alias, or omit the field and have an alias be generated for you.

            The response is your new alias:

            ```
            {
              "alias": "{{aliasName}}"
            }
            ```

            > ### Note:  
            > If you receive a 409 response code, the alias already exists in the vault. In this case, update your credentials in the vault using the following request and the same body you used to store your credentials:
            > 
            > ```
            > PUT /api/v1/dsi/credentials/token/{{aliasName}}
            > ```

        3.  You can now start the transfer process with the following call, entering your alias as `keyName`:

            ```
            POST /api/management/v3/transferprocesses
            																				{
                "@context": [
                {
                    "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
                },
                {
                    "edc": "https://w3id.org/edc/v0.0.1/ns/"
                }
                ],
                "@type": "edc:TransferRequest",
                "edc:protocol": "dataspace-protocol-http",
                "edc:counterPartyAddress": "{{providerControlPlaneDsp}}",
                "edc:contractId": "{{agreementId}}",
                "edc:assetId": "{{assetId}}",
                "edc:transferType": "AmazonS3-PUSH",
                "edc:dataDestination": {
                     "edc:type": "AmazonS3",
                	"edc:bucketName": "dsibucket-dev-consumer-001",
            	    "edc:region": "eu-central-1",
            	    "edc:folderName": "testConsumerFolder",
            	    "edc:objectName": "testfilename_10mb.txt",
            	    "edc:keyName": "{{aliasName}}"
                },
                "edc:privateProperties": {
                    "private-key": "private-value"
                }
            }
            ```



6.  For **Azure** assets, complete the following steps after getting your contract agreement ID.

    1.  Create credentials for your Azure access as a consumer of Data Space Integration using the [token API](https://int.api.hana.ondemand.com/api/DSIAPI/resource/STS_Credentials_Alias). Your credentials alias must follow the pattern `accountName-key1`, with `accountName` being your Azure account name.

        > ### Note:  
        > To create credentials in Data Space Integration, you need the role `CredentialsWrite`. This role is included in the role collection `DataspaceTechnicalAdmin`, but you can also assign the role to your user individually in the SAP BTP cockpit.

        > ### Caution:  
        > Make sure that the credentials are valid for the account. Since the credentials are cached in the control plane, it must be restarted to reflect any changes you make. In this case, please get in touch with support. See [Troubleshooting for Data Space Integration](troubleshooting-for-data-space-integration-166fa88.md).

    2.  Next, trigger the transfer process using the following payload. For Azure assets, the payload differs slightly from the S3 payload to account for the differing data destination. For more details, refer to the Transfer Process API and select an example for Azure.

        > ### Note:  
        > While the Eclipse Dataspace Connector supports the use of `blobName` and `keyName` in the data destination, Data Space Integration doesn't support these parameters. Please only use the parameters listed used in the following example payload.

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
           "edc:transferType": "AzureStorage-PUSH",
           "edc:dataDestination": {
               "type": "AzureStorage",
               "account": "{{accountName}}",
               "container": "{{container}}"
               "folderName": "destinationFolder/", //optional
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




<a name="loio4afdf5c06302482fb2fff87ed94f3896__result_sb4_qjz_pcc"/>

## Results

You've successfully closed a contract negotiation, received the contract agreement ID, and the provider transferred an asset into your bucket.

