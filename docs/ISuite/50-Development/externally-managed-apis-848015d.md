<!-- loio848015dfbb704293aec771ff84a21072 -->

# Externally Managed APIs

You can add and view APIs that are not managed by SAP Integration Suite but by some other API Management solution.

You can import an API definition \(Open API Specification 2.0 or 3.0\) of externally managed APIs in Integration Suite, without adding management capability \(proxy creation and policies\) of SAP Integration Suite and publish them to Developer Hub.



<a name="loio848015dfbb704293aec771ff84a21072__section_ql1_fyb_mnb"/>

## Features of Externally Managed APIs

-   Sometimes these APIs are managed by external gateways.
-   API Proxies are not created for these APIs.
-   These APIs are only listed in SAP Integration Suite. No aspect of their life cycle is managed by SAP Integration Suite.
-   Status \(Deployed/Not Deployed\) is not displayed for these APIs.
-   These APIs are represented by the symbol: ![](images/External_API_94e5ac7.png)
-   If you create a product using only externally managed APIs , your consumers can't view the rate plan for these APIs, nor can they subscribe to the product or use custom attributes for the product in the Developer Hub. For more information, see [Create a Product](create-a-product-d769622.md).
-   You can choose to manage the life cycle of these externally managed APIs after listing them. To do so, from the *Overview* page of the API, choose *Manage*.
-   You can list externally managed APIs by importing them. For more information, see [Import an API Definition](import-an-api-definition-9342a93.md).

**Related Information**  


[Adding Externally Managed APIs](adding-externally-managed-apis-523ff94.md "To add an externally managed API, you must import the API definition of an externally managed API in Integration Suite.")

