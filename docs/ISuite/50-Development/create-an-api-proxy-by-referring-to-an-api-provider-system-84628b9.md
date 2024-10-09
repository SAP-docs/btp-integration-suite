<!-- loio84628b9a16bd496391c9c26f5d4a4283 -->

# Create an API Proxy by Referring to an API Provider System

Create an API proxy by discovering or selecting one of the services available on the backend system configured by via the API provider.

**Prerequisite: The role collection *APIPortal.Administrator* should be assigned to you.**



<a name="loio84628b9a16bd496391c9c26f5d4a4283__section_imc_frp_pyb"/>

## Browse for an OData Service for an API Provider

If you want to browse for an OData service for a provider that you’ve already configured, proceed as follows:

1.  Log on to the Integration Suite.

2.  Choose *Configure* \> *APIs* from the left navigation pane.

3.  To expose a service as an API, choose *Create*.

4.  Select the *API Provider* radio button.

5.  Select the required open connector type provider from the *API Provider* dropdown list.

    The dropdown list contains the providers that you’re connected to. If the provider you need isn’t listed here, add it on the *Configure* tab.

6.  To view the list of OData services available in the provider, choose *Discover* and select the required service.

    If you deselect the *Link API Provider* checkbox, the API proxy is no longer linked to any API provider. It now acts just like a URL-based API. However, since the API created is originally of type OData, you can’t add or delete resources to it.

    Also, since such APIs aren’t linked to any API provider, you can’t use the *Synchronize* option to update the API with the latest version that might be available in the backend.

    > ### Note:  
    > When you discover an API provider, the fetched metadata for an API doesn't include the HEAD method for any resource. If your backend supports the HEAD method, you can include it by updating the API proxy specification in the API Designer.

7.  The details of the API *Name*, *Title*, *API Base Path*, *API State*, *Host Alias* and *Service Type* are automatically populated.

8.  Enter a short introductory text in the *Short Text* field.

9.  Optionally, enter a *Version* for your API proxy.

    When you choose to version your API proxy, its name is appended with the version, and its basepath are prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md).

10. Choose *Create*.

11. If you want to add SAP documentation annotations to the API documentation, choose *Yes* for *Documentation*.

    > ### Note:  
    > This field is only displayed if you’re fetching services from SAP Gateway Systems. For more information about SAP documentation annotations, see [Extended Support of Long Texts in the Metadata](http://help.sap.com/saphelp_gateway20sp10/helpdata/en/30/6e8c537c8fcc26e10000000a4450e5/frameset.htm).

12. Choose *Create*.

13. Complete the remaining steps by referring to the [Create an API Proxy](create-an-api-proxy-c0842d5.md) topic.




<a name="loio84628b9a16bd496391c9c26f5d4a4283__section_u45_frp_pyb"/>

## Browse for an Open Connector Instance for an API Provider

If you want to create a proxy for an Open Connector instance for a provider that you’ve already configured, proceed as follows:

1.  Log on to the Integration Suite.

2.  Choose *Configure* \> *APIs* from the left navigation pane.

3.  To expose a service as an API, choose *Create*.

4.  Select the *API Provider* radio button.

5.  Select the required open connector type provider from the *API Provider* dropdown list.

    The dropdown list contains the providers that you’re connected to. If the provider you need isn’t listed here, add it on the *Configure* tab.

6.  To view the list of OData services available in the provider, choose *Discover* and select the required service.

    If you deselect the *Link API Provider* checkbox, the API proxy is no longer linked to any API provider. It now acts just like a URL-based API. However, since the API created is originally of type OData, you can’t add or delete resources to it.

    Also, since such APIs aren’t linked to any API provider, you can’t use the *Synchronize* option to update the API with the latest version that might be available in the backend.

7.  The details of the API *Name*, *Title*, *API Base Path*, *API State*, *Host Alias* and *Service Type* are automatically populated.

    > ### Note:  
    > Name and basepath shouldn’t contain spaces.

8.  Enter a short introductory text in the *Short Text* field.

9.  Optionally, enter a *Version* for your API proxy.

    When you choose to version your API proxy, its name is appended with the version, and its basepath are prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md).

10. Choose *Create*.

    On creating the proxy, an encrypted key value map is created with the following name `apim.oc.instance.token` and key name `default`. Also, an open connector policy is attached to the incoming POST flow request of the target endpoint of the APIProxy.

    > ### Note:  
    > -   For an API Proxy, you can have only one open connector policy attached and the content of the open connector policy can’t be modified.
    > 
    > -   An API Proxy consists of a virtual host and a base path. The base path can be identical for multiple API proxies, provided the API proxies have different virtual hosts. This means, for an API Proxy, the combination of the virtual host and base path should be unique.
    > 
    >     The example below explains the same, where AP1 is proxy 1, AP2 is proxy 2, VH1 is Virtual Host 1, VH2 is the Virtual Host 2, and BP\(A\) is the base path.
    > 
    >     Example: AP1 = VH1+ BP\(A\)
    > 
    >     AP2 = VH2 + BP\(A\)
    > 
    > -   On deleting the proxy, the encrypted key value map created above is also deleted. Further, while exporting the API, encrypted key value map created above isn’t exported with the API.

11. Choose *Create*.

12. Complete the remaining steps by referring to the [Create an API Proxy](create-an-api-proxy-c0842d5.md) topic.


