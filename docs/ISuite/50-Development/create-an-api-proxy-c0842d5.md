<!-- loioc0842d5698eb4143b8cfa528b5435cf9 -->

# Create an API Proxy

This topic describes the steps to create an API proxy from the Integration Suite.



## Prerequisites

The role collection *APIPortal.Administrator* should be assigned to you.

To build APIs, you must do the following:

-   Make sure that you have the REST, OData, or SOAP URL of the service that you want to expose as an API.
-   Browse for a service on a specific API provider. To do so, you must configure the required API provider on the *Configure* tab.
-   You’ve created an instance against ORG/USER secret for creating an API Proxy from an Open Connector type API Provider.



## Context

Instead of consuming services directly, application developers can access API proxies exposed via API Management. You do so, by creating an API proxy that camouflages the service you want to expose. The API maps a publicly available HTTP endpoint to back-end services. Creating this API proxy lets API Management handle the security and authorizations required to protect, analyze, and monitor your services.



<a name="loioc0842d5698eb4143b8cfa528b5435cf9__steps_w2q_3hg_ks"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

    A list of APIs appears in the catalog.

    Alternatively, browse for a service on a specific API provider. To do so, you must configure the required API provider. You can view the number of calls made for an API in the current month. The data is visible for each API in the *Calls* column and also on the details screen of the individual API.

3.  To expose a service as an API, choose *Create*.

4.  Select the option based on your preference.


    <table>
    <tr>
    <th valign="top">

    Select...
    
    </th>
    <th valign="top">

    To...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *API Provider*
    
    </td>
    <td valign="top">
    
    [Create an API Proxy by Referring to an API Provider System](create-an-api-proxy-by-referring-to-an-api-provider-system-84628b9.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *API Proxy*
    
    </td>
    <td valign="top">
    
    [Create an API Proxy Based on an Existing API Proxy](create-an-api-proxy-based-on-an-existing-api-proxy-54831ca.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    [Create an API Proxy by Providing a Direct Target Endpoint URL](create-an-api-proxy-by-providing-a-direct-target-endpoint-url-d0f5087.md) 
    
    </td>
    </tr>
    </table>
    
5.  Select the appropriate tabs. You can choose from the following, *Overview*, *Proxy Endpoint*, *Target Endpoint*, *Resources, and* *Revisions*.


    <table>
    <tr>
    <th valign="top">

    Tab
    
    </th>
    <th valign="top">

    Details
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Overview
    
    </td>
    <td valign="top">
    
    You can edit the following:

    -   Name of the API
    -   Host Alias
    -   API Base Path
    -   API State
    -   API Description


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Endpoint
    
    </td>
    <td valign="top">
    
    You can add the proxy endpoint and the route rules.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Endpoint
    
    </td>
    <td valign="top">
    
    You can choose URL, API Provider, or API proxy, as the target endpoint as well as enter target endpoint rules.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Resources
    
    </td>
    <td valign="top">
    
    You can add resources.

    Resources refer to the individual endpoints or services that are exposed through APIs.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Revision
    
    </td>
    <td valign="top">
    
    Once an API is created, you can plan subsequent compatible changes to the API by creating a revision.
    
    </td>
    </tr>
    </table>
    
6.  Add a resource to refer to individual endpoints or services.

    > ### Note:  
    > -   For an OData service, all the associated artifacts appear on the different tab pages mentioned below. The *Resources* tab lists all the resources associated with the API. The API documentation with SAP documentation annotations, if selected, is also fetched from the metadata.
    > 
    > -   For a SOAP- and REST-based service, the *Resources* tab appears. Add the resources manually.

    > ### Note:  
    > In case you want to restrict your users from accessing all the resources associated with the API Proxy, you need to create a new Product, add the required API to the Product, and select the resources for which you want to provide access. For more information, see [Create a Product](create-a-product-d769622.md).![](images/Add_Resources_6351be2.png)

    -   For a *REST* service, add a resource as follows:

        1.  Choose + \(*Add*\).

        2.  In the popup, enter a title and path prefix for the resource.

        3.  Select the methods that need to be supported for this resource.

        4.  Add descriptions in the editor and choose *Add*.

            The added resource appears on the *Resources* tab.

        5.  Choose *Add* to add more resources to the same API.


    -   For a SOAP service, add a resource as follows:

        1.  Choose + \(*Add*\).

        2.  Enter a title and specify the SOAP operation name in the path prefix.

        3.  Use the editor to enter the relevant API documentation in the description field, and choose *Add*.

            The added resource appears on the *Resources* tab. By default, only the *POST* operation is selected.

        4.  Add descriptions in the editor and choose *Add*.

            The added resource appears on the *Resources* tab.

        5.  Choose *Add* to add more resources to the same API.


    -   For an OData service, select the methods that the application developer can perform:


    -   *Get*: Read an entity.
    -   *Post*: Create an entity.
    -   *Put*: Update an entity.

        > ### Note:  
        > API Management generates PUT operation as the default update operation. However, you can override the default update operation for API Proxy of type OData. For more information, see [Overriding the Default Update Operation for API Proxy of Type OData](overriding-the-default-update-operation-for-api-proxy-of-type-odata-4a12c59.md).

    -   *Delete*: Delete an entity.

        > ### Note:  
        > Only the supported methods for each resource appear on the UI. By default, only permitted methods are selected.


    For a given resource, choose *Show/Hide* to view the list of properties and their associated API documentation. You can add descriptions for each resource in the editor.

    > ### Note:  
    > For a given resource, choose *Open API Designer* and correct the errors in swagger definition, if any. The error message displayed on the screen helps in error detection and correction. Choose *Save* after making the necessary corrections in the swagger file.
    > 
    > See the example in the following screen: ![The example is based on the following error message: "Error in swagger definition, please correct the following errors and re-try missed comma between flow collection entries at line nine, column one." Therefore, you are not only informed by the kind of error, but also at which point in the swagger definition you will find it.](images/Swagger_definition_0fffa2e.png)

7.  To define policies on the API, go to the *Policies* tab. For more information about how to create a policy, see [Create a Policy](create-a-policy-c90b895.md).

8.  If you want to define multiple proxy endpoints, navigate to *Proxy EndPoint* tab.

    In the *Proxy Endpoint Properties*section, choose *Add*. Enter the *Property Name* and the *Values*. For the Proxy Endpoint property specifications, see [Proxy Endpoint Properties](proxy-endpoint-properties-1705a92.md).

9.  If you want to define multiple route rules, navigate to *Proxy EndPoint* tab. In the *Route Rules* section, choose *Add*.

    > ### Note:  
    > When the API is created, the default route rule is set. It points to the default target endpoint and no rule is attached to it. Use the option *None* to ensure that no request is routed to any target endpoint. If there are multiple route rules, the rules are evaluated in sequence as displayed on the screen.
    > 
    > For more information on how to define multiple target endpoints using Route Rule, see [Enable Dynamic Routing](enable-dynamic-routing-49cbe91.md).

10. To define target endpoint properties, navigate to the *Target EndPoint* tab and choose *Add*.

    Enter the *Property Name* and the *Values*. For the target endpoint property specifications, see [Target Endpoint Properties](target-endpoint-properties-edeed6a.md).

11. To define multiple target endpoints, navigate to the *Target EndPoint* tab.

    Choose *Add* next to the *Target EndPoint* dropdown menu.

    In the *Add Target EndPoint* dialog, fill in the target endpoint *Name*, select the *API Provider*, where you want the target endpoint to point to, and specify the *Relative URL*, then choose *Add*.

    > ### Note:  
    > Only target endpoints of the type API provider can be added in this dialog.

    > ### Note:  
    > If you have an API proxy with a multi-target endpoint, it is recommended that the name of the target endpoint should be between 2 and 255 characters. If you enter a single character in the name field for the provider types OpenConnector or Cloud Integration Flow, the API proxy cannot be deployed to the runtime.

    Once added, the target endpoint will appear in the *Target EndPoint* dropdown menu. You can also change the type of the target endpoint from API provider to API proxy or URL.

    To add policies to the target endpoint, choose *Policies* from the top-right corner of the page. You can then view the target endpoint flow and the policies applied to it in the*Policy Editor*. To view the policies associated with a different target endpoint, you can navigate back to the *Target EndPoint* tab on the proxy details page. Select the desired target endpoint and return to the *Policy Editor*.

12. Once you’ve filled in all the required details of the API, you can select one of the following two actions for the API:


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
    
    *Save* 
    
    </td>
    <td valign="top">
    
    *Not Deployed:*API is available only in the Integration Suite, and isn’t available for product assignments.
    
    </td>
    <td valign="top">
    
    *Deploy*

    API is deployed and is ready for product assignments.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Deploy* 
    
    </td>
    <td valign="top">
    
    *Deployed*: Only deployed APIs can be selected for product publishing.
    
    </td>
    <td valign="top">
    
    *Undeploy*

    If any API is undeployed after being published, it’s removed from the developer portal. When the API is deployed again, the product is updated. You can bring down an API without having to delete it from the product assignment. You can’t undeploy an API if it’s the only one associated with the product.
    
    </td>
    </tr>
    </table>
    



<a name="loioc0842d5698eb4143b8cfa528b5435cf9__postreq_gzn_mq2_qyb"/>

## Next Steps

Once you’ve created an API proxy, you can do the following:

**Related Information**  


[Create an API Proxy Using the API Designer](create-an-api-proxy-using-the-api-designer-26e1bbd.md "Model APIs in the Open API format that is available on the Integration Suite.")

