<!-- loio0174c4a53f5c41e59d22f0d4c5540597 -->

# Invoking an OData API



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You have deployed an OData API successfully; the service is in active status ready to be consumed.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  On the Overview page, in the section *Manage Integration Content*, choose the tile that shows the services with the status *Started*.

3.  Search for and open the service that you deployed.

4.  On the *Endpoints* tab, you can view the endpoint URI. This endpoint URI is the OData API Root URI.

5.  You can copy this URI by choosing the copy icon and invoke it from the calling application.

    You can invoke an OData API in*$batch* mode by appending the term */$batch* to the service root URI and invoking the same using the relevant payload.

    -   Currently only one operation is supported for each *changeset*.

    -   The Message Processing Log \(MPL\) is generated for each *changeset*

        > ### Note:  
        > If your MPL shows an error message **FAILED** without any error in the trace, then it means that your Response does not match the Metadata defined in the adapter.

    -   To obtain a JSON response, add **Accept HTTP header** with application/json value.
    -   All the headers available in the integration flow pipeline at the time of message processing, will be returned as response headers when the OData API is invoked.
    -   POST calls support deep structure responses.



