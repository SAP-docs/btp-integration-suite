<!-- loio57abb0096ccf40ed970734b7e3d63a30 -->

# Creating a Versioned API

Creating a versioned API Proxy from a deployed, versioned, or nonversioned API Proxy in the API Management, API Portal.



## Context

You can create a versioned API Proxy, from either a previously versioned API or a nonversioned API that have been deployed, from the API Portal. To know more about creating a versioned API Proxy when creating it from scratch in the API Portal, see [API Versioning](api-versioning-b3cda3b.md).



## Procedure

1.  Log on to the API portal.

2.  From the navigation bar, choose ![](images/develop_4910d07.png) \(Develop\).

    A list of APIs appears in the catalog.

3.  Select the API from which you want to create a new versioned API. This can be either already versioned API, or a nonversioned API.

4.  From the top-right corner of the *Overview* screen, choose *...* \> *New Version*.

5.  In the *Create New Version* screen, in the *Version* field, enter a new version and choose *Create*. You can’t edit the name and the base path. However, once you enter a new version, the version is appended to the name and prepended to the base path to create a unique API Proxy version.

    If the version you enter is v1, the name will be Name\_v1, and the basepath will /v1/SalesOrder.

6.  You can then choose to *Save* or *Deploy* the new version of this API Proxy.


