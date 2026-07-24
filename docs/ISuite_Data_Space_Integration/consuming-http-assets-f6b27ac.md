<!-- loiof6b27ac5837349cfab087d6f399602b1 -->

# Consuming HTTP Assets

Consume an HTTP asset your negotiated beforehand.



<a name="loiof6b27ac5837349cfab087d6f399602b1__prereq_lvb_njd_2zb"/>

## Prerequisites

-   You've discovered the provider's catalog and selected an offer that's right for you. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).

-   You've triggered the contract negotiation. See [Triggering a Contract Negotiation](triggering-a-contract-negotiation-dc11922.md).




## Context

This topic describes the recommended process for consuming HTTP assets.

For other processes of transferring assets, see [Consuming Assets Into S3 Storage](consuming-assets-into-s3-storage-4afdf5c.md) and [Consuming Assets Into Azure Blob Storage](consuming-assets-into-azure-blob-storage-0088840.md).



## Procedure

1.  Trigger the transfer process with the following payload:

    ```
    POST /api/dsi/v1/transfer-process
    
    {
      "name": "My HTTP Pull Transfer",
      "counterPartyAddress": "https://provider.example.com/api/v1/dsp",
      "agreementId": "urn:uuid:a1b2c3d4-e5f6-7890-abcd-ef1234567890",
      "transferProcessType": "HttpData-PULL"
    }
    ```

    As result, you receive the **transfer process ID**.

2.  Confirm that the transfer process has reached the status **COMPLETED** before continuing.

3.  Next, fetch the EDR associated with your transfer process with the following GET call, adding the transfer process ID:

    ```
    GET /api/dsi/v1/transfer-process/{id}/edr
    ```

    In the EDR details, you can find the URL \(`endpoint`\) and the authorization token \(`authCode` and `authorization`\) with which you can access the asset's details.

4.  Call the provider data plane and retrieve the asset.

    > ### Restriction:  
    > Only HTTPS connections are supported. If the asset provider relies on HTTP connections to provide assets, the data transfer is disrupted due to security concerns.




## Results

You've retrieved the asset that you negotiated.

