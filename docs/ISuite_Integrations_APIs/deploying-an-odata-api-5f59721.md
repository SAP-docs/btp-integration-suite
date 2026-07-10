<!-- loio5f59721676574d3d88d9675e1851de27 -->

# Deploying an OData API



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You've created anOData API artifact with a valid OData model. You've provided binding information for at least one OData object in the model. You've verified that all integration flows are valid.

You can use this procedure to deploy the OData API.



## Procedure

1.  Choose *Deploy* on the Service Designer page.

2.  Confirm that you do want to deploy. If there are no validation errors, a message is displayed confirming that the service is triggered for deployment.

3.  Choose *OK*. The OData API is now deployed.

    The OData API starts on the tenant, after deployment. You can confirm that the status of theOData API is *Started* in the Integration Content Monitor. For more information, see [Manage Integration Content](manage-integration-content-09a7223.md).

    It can take a few moments for the OData API to get active. Once it's active, the OData API is ready for consumption.

    > ### Note:  
    > The URL of the OData API endpoint is derived from the name of the OData API artifact.


