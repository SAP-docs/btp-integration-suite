<!-- loio008884076c3346df94fd0bc67fa0b7d8 -->

# Consuming Assets Into Azure Blob Storage

Transfer assets to your desired location in Azure Blob Storage.



<a name="loio008884076c3346df94fd0bc67fa0b7d8__prereq_zjj_x1d_2zb"/>

## Prerequisites

-   You've discovered the provider's catalog and selected an offer that's right for you. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).

-   You've triggered the contract negotiation. See [Triggering a Contract Negotiation](triggering-a-contract-negotiation-dc11922.md).




## Context

This topic describes the recommended process to transfer hyperscaler-based assets to your Azure Blob Storage.

For the process of transferring assets to your S3 storage, see [Consuming Assets Into S3 Storage](consuming-assets-into-s3-storage-4afdf5c.md). For HTTP assets, see [Consuming HTTP Assets](consuming-http-assets-f6b27ac.md).



## Procedure

1.  Before you can trigger the transfer process, decide how you want to grant access to your Azure account details when triggering the transfer process: You can either use an **account key** or a **SAS token**. For more information about SAS tokens, see [Shared access signature \(SAS\) tokens for storage containers](https://learn.microsoft.com/en-us/azure/ai-services/translator/document-translation/how-to-guides/create-sas-tokens?tabs=Containers).

2.  Now that you have your contract agreement ID and decided on your authorization method, trigger the transfer process with the following payload:

    ```
    POST /api/dsi/v1/transfer-process
    {
        "name": "<transfer-process-name>",
        "counterPartyAddress": "<provider-connector-endpoint>",
        "transferProcessType": "AzureBlob-PUSH",
        "agreementId": "<contract-agreement-id>",
        "dataDestination": {
            "type": "AZURE_BLOB",
            "account": "<storage-account-name>",
            "container": "<consumer-container-name>",
            "folderName": "<folder-name>", // optional if you want to specific folder path in target container
            "objectName": "<blob-name>", // optional if you want to specify blob name for single blob transfer
            "accountKey": "<account-key>", // optional if you wants to use account key instead of SAS token
            "sasToken": "<sas-token>", // optional if you want to use SAS token 
        }
    }
    ```

3.  After triggering the transfer process, you can check its status with the following GET call:

    > ### Code Syntax:  
    > ```
    > /api/dsi/v1/transfer-process/{id}/state
    > ```

    Once the status reaches *successful*, you can find the asset in the bucket you defined in the transfer process payload.




<a name="loio008884076c3346df94fd0bc67fa0b7d8__result_sb4_qjz_pcc"/>

## Results

The provider transferred the asset that you negotiated into your storage.

