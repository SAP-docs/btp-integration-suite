<!-- loiodb55f0d917754e999954c2796b11b114 -->

# Basic Authentication with clientId and clientsecret for API Clients

You can use basic authentication based on the user credentials \(clientid and clientsecret\) that are generated with the service key.



## Context



When you select this option, the user associated with the sender system's request is authenticated based on the user credentials \(using basic authentication. `clientid` and `clientsecret`\) that are generated with a service key.

> ### Note:  
> This option is **not** recommended for productive scenarios.

For more information, see: [Basic Authentication](basic-authentication-2c4c2d9.md) \(explains the concepts and how this authentication option works\).

In detail, perform the following steps:



<a name="loiodb55f0d917754e999954c2796b11b114__steps_ifg_1vy_cpb"/>

## Procedure

1.  Look up the role that's used to authorize the API client to access the related Cloud Integration resource using the API. This can be either a standard role such as `AuthGroup_ReadOnly`, or a custom role. For more information, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

2.  In SAP BTP cockpit, select the subaccount that hosts your SAP Integration Suite virtual environment and create a service instance and service key.

    Proceed as described under [Creating Service Instance and Service Key for Inbound Authentication](creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).

    For this use case, specify the service instance and service key parameters as follows:

    ****


    <table>
    <tr>
    <th valign="top" colspan="3">

    Service Instance
    
    </th>
    <th valign="top" colspan="4">

    Service Key
    
    </th>
    </tr>
    <tr>
    <th valign="top">

     
    
    </th>
    <th valign="top">

    Roles
    
    </th>
    <th valign="top">

    Grant-types
    
    </th>
    <th valign="top">

     
    
    </th>
    <th valign="top">

    External Certificate
    
    </th>
    <th valign="top">

    Validity
    
    </th>
    <th valign="top">

    Key Size
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *api* 
    
    </td>
    <td valign="top">
    
    Keep a standard role such as `AuthGroup_ReadOnly`, or use one or more custom roles.
    
    </td>
    <td valign="top">
    
    *Client Credentials* 
    
    </td>
    <td valign="top">
    
    *ClientId/Secret* 
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    </tr>
    </table>
    
3.  Call the OData API.

    1.  For the address of the call, enter the address of the OData API resource and the query options \(see [HTTP Calls and URI Components](../http-calls-and-uri-components-ca75e12.md)\).

    2.  Choose *Basic Authentication* as your authentication option, and make sure to use the clientid / clientsecret that you generated with the service key.


    For more information, see [OData API](../odata-api-a617d6f.md) .


