<!-- loiod0f50871e0bb49c094129efd3c9ac304 -->

# Create an API Proxy by Providing a Direct Target Endpoint URL

Create an API proxy of the type REST and SOAP using the HTTP endpoint URL.



<a name="loiod0f50871e0bb49c094129efd3c9ac304__section_kzk_1qh_c1c"/>

## Prerequisite

The role collection *APIPortal.Administrator* should be assigned to you.



<a name="loiod0f50871e0bb49c094129efd3c9ac304__section_i1n_tvw_pyb"/>

## Create an API Proxy of the type OData

1.  Select the *URL* radio button.

2.  Enter the OData service URL in the *URL* field. For example, http://<host\>:<port\>/SFlight.

    > ### Note:  
    > Ensure that the service URL you provide doesn’t redirect to a different URL. That is, check if the service URL you’re trying to access is temporarily or permanently moved to a different location. If it does so, then it’s recommended that you provide the new location \(redirected URL, if exists\) of the service. For more information about how to handle URL redirection, see [Handling URL Redirects in an API Proxy Using Policies](handling-url-redirects-in-an-api-proxy-using-policies-9e63c01.md).

3.  Enter the *Name* and *Title*, and provide an introductory text in the *Short Text* field, for the API.

    > ### Note:  
    > For API names, use only alphanumeric characters, underscores \(\_\), and hyphens \(-\). Don't start names with a hyphen.

4.  Optionally, enter a version for your API Proxy.

5.  When you choose to version your API Proxy, its name is appended with the version, and its basepath is prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md).

6.  Select a virtual host alias from the *Host Alias* dropdown.

7.  In the *API Base Path* field, provide a path prefix for the API. For example, v1/SFlight.

8.  In the *Service Type* field, enter `OData`.

9.  Choose *Create*.

10. Complete the remaining steps by referring to the [Create an API Proxy](create-an-api-proxy-c0842d5.md) topic.




<a name="loiod0f50871e0bb49c094129efd3c9ac304__section_sb3_5vw_pyb"/>

## Create an API Proxy of the type REST

1.  Select the *URL* radio button.

2.  Enter the REST service URL in the *URL* field. For example, http://<host\>:<port\>/SFlight.

    > ### Note:  
    > Ensure that the service URL you provide doesn’t redirect to a different URL. That is, check if the service URL you’re trying to access is temporarily or permanently moved to a different location. If it does so, then it’s recommended that you provide the new location \(redirected URL, if exists\) of the service. For more information about how to handle URL redirection, see [Handling URL Redirects in an API Proxy Using Policies](handling-url-redirects-in-an-api-proxy-using-policies-9e63c01.md).

3.  Enter the *Name* and *Title*, and provide an introductory text in the *Short Text* field, for the API.

    > ### Note:  
    > For API names, use only alphanumeric characters, underscores \(\_\), and hyphens \(-\). Don't start names with a hyphen.

4.  Optionally, enter a version for your API Proxy.

5.  When you choose to version your API Proxy, its name is appended with the version, and its basepath is prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md).

6.  Select a virtual host alias from the *Host Alias* dropdown.

7.  In the *API Base Path* field, provide a path prefix for the API. For example, v1/SFlight.

8.  In the *Service Type* field, enter `REST`.

9.  Choose *Create*.

10. Complete the remaining steps by referring to the [Create an API Proxy](create-an-api-proxy-c0842d5.md) topic.




## Create an API Proxy of the type SOAP

1.  Select the *URL* radio button.

2.  Enter the SOAP service URL in the *URL* field. For example, http://<host\>:<port\>/SFlight.

    > ### Note:  
    > Ensure that the service URL you provide doesn’t redirect to a different URL. That is, check if the service URL you’re trying to access is temporarily or permanently moved to a different location. If it does so, then it’s recommended that you provide the new location \(redirected URL, if exists\) of the service. For more information about how to handle URL redirection, see [Handling URL Redirects in an API Proxy Using Policies](https://help.sap.com/docs/sap-api-management/sap-api-management/handling-url-redirects-in-api-proxy-using-policies).

3.  Enter a name and description for the API.

4.  Optionally, enter a version for your API Proxy.

5.  When you choose to version your API Proxy, its name is appended with the version, and its basepath is prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is /v1/SalesOrder. For more information, see [API Versioning](api-versioning-b3cda3b.md).

6.  Select a virtual host alias from the *Host Alias* dropdown.

7.  In the *API Base Path* field, provide a path prefix for the API. For example, v1/SFlight.

8.  In the *Service Type* field, enter `SOAP`.

9.  Choose *Create*.

10. Complete the remaining steps by referring to the [Create an API Proxy](create-an-api-proxy-c0842d5.md) topic.


