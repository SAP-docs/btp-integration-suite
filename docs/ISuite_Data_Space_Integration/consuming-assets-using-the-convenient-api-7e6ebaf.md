<!-- loio7e6ebaf81f9f4ebdb5c7e3a0bee585cf -->

# Consuming Assets Using the Convenient API

The Convenient Data Request API automates the complete data exchange workflow by handling catalog lookup, negotiation, and transfer in a single request. Use this API to simplify data asset consumption without managing individual workflow steps.



## Overview

The **Convenient Data Request API** orchestrates the full data exchange workflow for you. You can access it at the SAP Business Accelerator Hub under [Convenient Data Request](https://hub.sap.com/api/DSIAPI/resource/Convenient_Data_Request).

Using this API, you can create a request using only a POST and GET call. The POST call handles the catalog lookup, negotiation, and transfer automatically, while you can use the GET call to look up the active workflow.



## Prerequisites

The unique asset that you want to consume must be unambiguously identifiable using the catalog filter. If the filter isn't specific enough, the API call results in an error.



## Payloads

For full example payloads, access the API references on the SAP Business Accelerator Hub at [Convenient Data Request](https://hub.sap.com/api/DSIAPI/resource/Convenient_Data_Request).



### POST Calls

You can create the following **POST** requests to trigger the workflow:

-   HTTP pull request, with or without a catalog filter
-   Azure blob push request
-   S3 push request

> ### Note:  
> For **push** requests, the convenient API triggers the transfer, but the actual transfer of the asset payload happens outside of the convenient API.



### GET Calls

Create GET calls to do the following:

-   Retrieve the status of your request

    > ### Caution:  
    > The orchestration is performed asynchronously in the background. Avoid polling for a status update more often than every 15 seconds.

-   For HTTP assets: retrieve the HTTP data

