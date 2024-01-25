<!-- loio9342a932441e45cd9636eb0a01a89958 -->

# Import an API Definition

This topic describes how to import an existing API definition into the Integration Suite.



## Prerequisites

The role collection *APIPortal.Administrator* should be assigned to you.

The API proxy content is available as a .zip file and swagger json file. The contents adhere to the API proxy structure as defined in [API Proxy Structure](api-proxy-structure-4dfd54a.md).

> ### Note:  
> -   If your API proxy uses an API provider that belongs to the type Cloud Integration flow, import of such an API proxy is currently not supported.
> 
> -   Ensure that the API proxy name in the <`APIProxyName`\>.xml file and the value of the *base\_path* field \(inside the APIProxyEndpoint file\) is unique.
> 
> -   *APIResources*, *Documentation**FileResource*, and *Policy* folders are not required in the .zip file.
> -   Ensure that the resource documentation is available in a single **OAS\_json** file. Note that you cannot refer to external links in the API definitions within this json file.
> -   API Management supports import of API definitions in both OAS 2.0 and OAS 3.0.
> 
>     To know more about OAS 3.0 support in API Management, see [OpenAPI Specification 3.0](openapi-specification-3-0-3ce080d.md).
> 
> -   Optional: If you want to mention the API State of the API proxy you are importing, you need to update the following in the API proxy XML:
>     -   API State: The state of the API proxy. To know more about API States, see [API Proxy States](api-proxy-states-091cda4.md)
>     -   Successor API: If the API state of the API proxy you are importing is deprecated or decomissioned, you need to provide information about a succesor API that the consumer should use.
>     -   Release Metadata: If the API state of the API proxy you are importing is deprecated or decomissioned, use this field to provide information about the following:
> 
>         -   Reason for deprecation or decomissioning
>         -   Date of deprecation or decomissioning
>         -   External succesor API: If you provide an external sucessor API, you will not use the Sucessor API parameter.
>         -   Changed By
>         -   Changed At
> 
>         > ### Sample Code:  
>         > ```
>         > <APIState>Deprecated</APIState>
>         > 
>         > <successorAPI>XYZ</successorAPI>
>         > 
>         > <releaseMetadata>{"reason":"undefined","date":1603132200000,"externalSuccessorAPI":"","changed_at":1602578356857,"changed_by":"xxx@abc.com"}</releaseMetadata>
>         > ```

**File Resource** is a script or code snippet that can be attached to Flows using policies. An API proxy container supports definition of a number of Java, Python or XSL scripts. These scripts can be executed in the context of either a Java Script, Python Script or XSL Transformation policy. Once a Script is defined, it can be applied as a either a Java Script policy, Python Script policy or XSL Transform policy in different Flows.



## Context

API Management provides the option to import an API definition.

> ### Note:  
> When an API proxy is transported or exported individually or as a part of a product, by default, it gets imported to the target in the deployed state.

> ### Note:  
> The API proxy zip can be successfully imported only if the providers associated with the API proxy in the source system are also present in the target system.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  On the *APIs* tab page, choose *Create* \> *Import API*.

4.  In the *Import API* window:

    1.  Choose *Browse*. Navigate and choose the required API from your local file system.

        You can attach files of type .zip and .json.When you import the API, you can create a new API or replace the existing API across landscapes seamlessly.

        You can include the configurations for health monitor and load balancer in the .zip file. For more information, see [Load Balancing Across API Providers](load-balancing-across-api-providers-7ac0c09.md).

    2.  You can choose to import either an API whose lifecycle will be managed by API Management, or an externally managed API, when importing the json file. Choose *Manage this API* to import an API whose lifecycle is to be handled by API Management.

    3.  Select a virtual host alias from the *Virtual Host* drop down.

    4.  If you want to version your API when uploading the .json file, select *Yes* for the *Create a Version* toggle button \(this is set to *No* by default\), and enter the version in the *Version* field that appears. The version will be appended to the name and prepended to the base path of the API, to create a unique API proxy version. For example, If the version you enter is v1, the name will be Name\_v1, and the basepath will be /v1/SalesOrder. To know more about versioning your API, see [API Versioning](api-versioning-b3cda3b.md).

    5.  If you want to list an externally managed API, when uploading the json file, choose *List as Externally Managed API*. This API will only be listed in SAP Integration Suite, and it's lifecycle will not be managed. For more information, see [Externally Managed APIs](externally-managed-apis-848015d.md).


5.  Choose *OK*.

    > ### Note:  
    > The API state remains unchanged during import.


**Related Information**  


[Export an API Definition](export-an-api-definition-420abb6.md "Once you create an API in the Integration Suite, you can choose to export it.")

