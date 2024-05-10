<!-- loio23974d6325c14d82bd2872c3050359e7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Copy an API Proxy

You can copy an API proxy in the same subscription.



<a name="loio23974d6325c14d82bd2872c3050359e7__prereq_rnp_v53_b2b"/>

## Prerequisites

You are assigned with *APIPortal. Administrator* role.



<a name="loio23974d6325c14d82bd2872c3050359e7__context_snp_v53_b2b"/>

## Context

To copy an API proxy, proceed as follows:



<a name="loio23974d6325c14d82bd2872c3050359e7__steps_tnp_v53_b2b"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  On the *APIs* tab page, choose the <span class="SAP-icons-V5"></span> Action icon against the required API and then select the *Copy* option. Alternatively, you can open the required API and in the details page select the option *Copy*.

4.  In the *Copy API*, the details for each attribute is pre filled. The *Name* and *API Base Path* fields should be unique. So, it is required to change the API *Name* and *API Base Path* values. The values for the remaining fields \(*Title*, *Short Text*, *API State*, and *Host Alias*\) can either be reatined or changed.

    1.  Optional: Enter a version for your API proxy.

        When you choose to version your API proxy, it's name will be appended with the version, and it's basepath will be prepended with the version. For example, If the version you enter is v1, the name will be Name\_v1, and the basepath will be /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md)


    For more details on each field, see [Create an API Proxy](create-an-api-proxy-c0842d5.md).

5.  Choose *Copy*.

6.  After you have copied the API, you can select one of the following two actions for the API:


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Resulting API State
    
    </th>
    <th valign="top">

    Future Action on API
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Save as Draft* 
    
    </td>
    <td valign="top">
    
    *Not Deployed*

    API is available only in the Integration Suite, and is not available for product assignments.
    
    </td>
    <td valign="top">
    
    *Deploy*

    API is deployed and is ready for product assignments.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Save and Deploy* 
    
    </td>
    <td valign="top">
    
    *Deployed*

    Only deployed APIs can be selected for product publishing.
    
    </td>
    <td valign="top">
    
    *Undeploy*

    If any API is undeployed after being published, it is removed from the developer portal. When the API is deployed again, the product is updated. You can bring down an API without having to delete it from the product assignment. You cannot undeploy an API if it is the only one associated with the product.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > An API proxy consists of a virtual host and a base path. The base path can be identical for multiple API proxies, provided API proxies have different virtual hosts. This means, for an API proxy, the combination of the virtual host and base path should be unique.
    > 
    > The example below explains the same, where AP1 is proxy 1, AP2 is proxy 2, VH1 is Virtual Host 1, VH2 is the Virtual Host 2, and BP\(A\) is the base path.
    > 
    > Example: AP1 = VH1+ BP\(A\) AP2 = VH2 + BP\(A\)


**Related Information**  


[Import an API Definition](import-an-api-definition-9342a93.md "This topic describes how to import an existing API definition into the Integration Suite.")

[Export an API Definition](export-an-api-definition-420abb6.md "Once you create an API in the Integration Suite, you can choose to export it.")

[Create an API Proxy Using the API Designer](create-an-api-proxy-using-the-api-designer-26e1bbd.md "Model APIs in the Open API format that is available on the Integration Suite.")

