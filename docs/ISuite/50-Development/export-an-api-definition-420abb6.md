<!-- loio420abb6ec7564c97b786c184b4fa0746 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Export an API Definition

Once you create an API in the Integration Suite, you can choose to export it.



## Prerequisites

The role collection *APIPortal.Administrator* should be assigned to you.

You have created an API in the Integration Suite with:

-   Relevant resources and documentation.
-   Policies attached to the API.



## Context

To export an API proxy, proceed as follows:



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  On the *APIs* tab page, choose the <span class="SAP-icons-V5"></span> Action icon against the required API and then select the *Export* option.

4.  Alternatively, you can open the required API, choose the breadcrumb and then select the option *Export*.

5.  A .zip file is exported with contents as described in the [API Proxy Structure](api-proxy-structure-4dfd54a.md). All the content related to the API documentation is available in Swagger\_json file. `The current state of the API, will also be available in the exported zip`.

    > ### Note:  
    > The API state and related metadata are not exported.


**Related Information**  


[Import an API Definition](import-an-api-definition-9342a93.md "This topic describes how to import an existing API definition into the Integration Suite.")

