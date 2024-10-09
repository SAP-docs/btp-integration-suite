<!-- loio4afdf5c06302482fb2fff87ed94f3896 -->

# Consuming S3 Assets

To consume assets, you must agree with the provider on the conditions. This process happens in a contract negotiation, after which you can transfer your assets.



<a name="loio4afdf5c06302482fb2fff87ed94f3896__prereq_zjj_x1d_2zb"/>

## Prerequisites

You've completed the steps described in [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md), in which you discovered the provider's catalog and selected an offer that's right for you.



## Context

This topic describes the recommended process to trigger a contract negotiation and transfer Amazon S3 assets. For the process for HTTP assets, see [Consuming HTTP Assets](consuming-http-assets-735300c.md).



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
    >     "@context": {
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

5.  You can now transfer your assets. Since you're using the S3 data plane, your request must include a data destination. This section is designated for your bucket details, which is where relevant objects are transferred to from the provider EDC.

    > ### Note:  
    > If you want to transfer S3 files that are bigger than 5 GB, open a ticket on `LOD-HCI-PI-OPS` before initiating the transfer process.

    You have two options for using credentials in your call: you can either use a **permanent access key ID and access key secret**, or generate an **alias** using the AWS Secret Token Service \(STS\).

    -   If you're using a **permanent access key ID and access key secret**, start the transfer process with the following POST call and body:

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

    -   As an alternative to using the permanent accessKeyId an secretAccessKey, you can also use an **alias**. The AWS Secure Token Service \(STS\) enables you to use temporary security credentials for AWS services. You can generate STS credentials, use these temporary credentials to receive an alias, and use this alias when initiating a transfer for S3 assets as a consumer.

        To use an STS alias, perform the following steps:

        1.  Generate STS credentials using the AWS command-line interface. For instructions and more information, see [Temporary security credentials in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html), [Request temporary security credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html) and [AWS STS examples using AWS CLI](https://docs.aws.amazon.com/cli/v1/userguide/cli_sts_code_examples.html)in the AWS documentation.

            The credentials consist of the following fields, which you'll need to enter in the next step:

            -   `accessKeyId`: A temporary access key ID that was generated by AWS

            -   `secretAccessKey`: A temporary secret access key that was generated by AWS

            -   `sessionToken`: A token used to validate your temporary security credentials

            -   `expiration`: Once your temporary security credentials have expired, you must generate new credentials.


        2.  To store your credentials in the vault of Data Space Integration, perform the following API call:

            ```
            POST /api/v1/dsi/credentials/token
            									
            									{
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



6.  Once you've triggered the transfer process, you can check its status with the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/transferprocesses/{id}/state
    > ```

    You can also receive general information about your transfer process with the following GET call:

    > ### Code Syntax:  
    > ```
    > {{managementURL}}/api/management/v3/transferprocesses/{id}
    > ```




<a name="loio4afdf5c06302482fb2fff87ed94f3896__result_sb4_qjz_pcc"/>

## Results

You've successfully closed a contract negotiation, received the contract agreement ID, and transferred an asset.

