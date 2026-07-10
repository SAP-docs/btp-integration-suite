<!-- loio15c7d528449c4636abc2a1120f5ab8e9 -->

# Test Runtime Behavior of APIs

Use the API Test Environment to test the runtime behavior of APIs.

The *Test Environment* enables you to test your APIs. Testing an API is essential to understand the runtime behavior of the APIs. It allows you to explore the resources associated with an API and execute the operations. It also allows you to test OData and REST-based services.

> ### Note:  
> This document describes the new design of Developer Hub. To view the documentation for the classic design, see [Test API Proxies](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/3ba6151391bc474b9f1fa69455f65e3b.html "Use the API Test Console to test the runtime behavior of the API proxies.") :arrow_upper_right:.



<a name="loio15c7d528449c4636abc2a1120f5ab8e9__section_yt3_f4f_tvb"/>

## Pre-requisite

The *Test Environment* tab will be visible to you only if you have the *AuthGroup.API.ApplicationDeveloper* role.



<a name="loio15c7d528449c4636abc2a1120f5ab8e9__section_bpw_tzh_dvb"/>

## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Test Environment*.

3.  A list of APIs appears on the left.
4.  Select the required API.

    The URL for the selected API is populated automatically in the *API Test Console*. For the selected API, the URLs of the supported resources appear in the dropdown list. One resource is selected by default.

5.  If you want to choose a different collection, use the dropdown list to select the required collection
6.  If you have the URL of the service that contains the API, enter the service URL.
7.  Choose *Authentication* to select the required type of authentication. You can choose from the following options:
    1.  *None*: No authentication required.
    2.  *Basic Authentication*: Provide a user name and password.

8.  Enable the required method:
    -   *GET*: Reads an entity
    -   *POST*: Creates an entity
    -   *PUT*: Updates an entity
    -   *DELETE*: Deletes an entity

        > ### Note:  
        > You can enable only the methods supported by the service.


9.  Enter the *Request Body* for PUT and POST methods.
10. Choose *Header* to add a header.

    > ### Note:  
    > If you want to add multiple headers, choose *Add Request Headers*.

11. Choose *Url Params* to enter the query parameter and value.

    > ### Note:  
    > If you want to add multiple query parameters, choose the button *Add URL Params*. Test Console supports passing of custom headers such as X-sap-apimgt-proxy-host:-proxy-trai and X-sap-apimgt-proxy-port:- 8080

12. Choose *Send.* 

    The response appears in the tabs:

    -   *Body*: View the formatted response.
    -   *Body \(Raw\)*: View the unformatted response.
    -   *Headers*: View the headers.
    -   *Cookies*: View the cookies.

13. If you want to use the response body as an input request, choose *Use as Request* on the *Body \(Raw\)* tab.
14. To view the transactions based on the testing activity that you did, choose *Launch API Viewer*. For more information on tracing API proxy, see [Debug an API Proxy](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/fb2c7aa34cdc443294a325ccb7876785.html "You debug an API proxy to troubleshoot and monitor them in SAP API Management, by probing the details of each step through the API proxy flow.") :arrow_upper_right:.

