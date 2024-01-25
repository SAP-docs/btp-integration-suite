<!-- loio26e1bbd2f3864b53a288e25786eb94e0 -->

# Create an API Proxy Using the API Designer

Model APIs in the Open API format that is available on the Integration Suite.



## Prerequisites

The role collection *APIPortal.Administrator* should be assigned to you.

To build API proxies, you must have the REST, OData, or SOAP URL of the service that you want to expose as an API.



## Context

The API designer editor includes rich inbuilt capabilities that enable you to do the following:

-   Import existing open APIs
-   Download APIs
-   Generate equivalent HTML output views
-   Save APIs
-   Validate open API syntax

The API designer supports OAS 2.0 and OAS 3.0 versions.

To know more about OAS 3.0 support in API Management, see [OpenAPI Specification 3.0](openapi-specification-3-0-3ce080d.md).



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

    A list of APIs appears in the catalog.

3.  To model an API in Open API format, choose *Create in API Designer*.

    > ### Note:  
    > -   You can now create your API in the embedded API designer
    > -   To update an existing API, select the API and choose *Edit in API Designer*.

4.  Enter the API-related information and choose *Save*. For information on how to model the API, see [API Designer](api-designer-51f3ca1.md).

5.  You can choose to version your the API, by selecting *Save* \> *Save as Version*, and entering a new value in the *Version* field. To know more about versioning your API, see [API Versioning](api-versioning-b3cda3b.md)

    When you choose to version your API proxy, it's name will be appended with the version, and it's basepath will be prepended with the version. For example, If the version you enter is v1, the name will be Name\_v1, and the basepath will be /v1/SalesOrder.


**Related Information**  


[Create an API Proxy](create-an-api-proxy-c0842d5.md "This topic describes the steps to create an API proxy from the Integration Suite.")

