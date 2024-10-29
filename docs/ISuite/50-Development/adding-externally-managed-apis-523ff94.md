<!-- loio523ff94ad5c8439987c78e17265ba882 -->

# Adding Externally Managed APIs

To add an externally managed API, you must import the API definition of an externally managed API in Integration Suite.



<a name="loio523ff94ad5c8439987c78e17265ba882__prereq_tfz_tj3_tzb"/>

## Prerequisites

-   You are assigned with *APIPortal. Administrator* role.

-   To import an externally managed API, you need to have or create an OpenAPI file for it.

    The OpenAPI file should specify the URL of the API. If you don't have an OpenAPI specification for your API, you can create one using various open-source editors or the API Designer included within Integration Suite. For more information, see [Create an API Using the API Designer](https://help.sap.com/docs/integration-suite/sap-integration-suite/create-api-from-api-designer?q=API%20Designer). Also, refer to the "Prerequisites" section in [Import an API Definition](import-an-api-definition-9342a93.md).




## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  On the *APIs* tab page, choose *Create* \> *Import API*.

4.  In the *Import API* window:

5.  Browse and select the required API definition from your local file system.

    You can attach files of type .zip and .json.

6.  To list an externally managed API, choose *List as Externally Managed API*.

    This API will only be listed in SAP Integration Suite, and it's lifecycle will not be managed.

    In order to access externally managed APIs in the Developer Hub, you need to add these APIs to a product and then publish the product. For more information on how to create a product, see [Create a Product](https://help.sap.com/docs/integration-suite/sap-integration-suite/create-product?q=import%20an%20APi&version=CLOUD).

    > ### Note:  
    > While you can add externally managed APIs to a product, you will not be able to include rate plans or add custom attributes for them.
    > 
    > If your product consists solely of externally managed APIs, users will not be able to subscribe to the product.


