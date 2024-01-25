<!-- loio647eeb3eca5d4c299009cacd1332247e -->

# Basic Authentication with clientId and clientsecret for Integration Flow Processing

Use this procedure to connect a sender system to SAP Cloud Integration.



## Context

When you select this option, the user associated with the sender system's request is authenticated based on the user credentials \(using basic authentication. `clientid` and `clientsecret`\) that are generated with a service key.

> ### Note:  
> This option is **not** recommended for productive scenarios.

For more information, see: [Basic Authentication](basic-authentication-2c4c2d9.md) \(explains the concepts and how this authentication option works\).

In detail, perform the following steps:

> ### Tip:  
> The configuration steps to create service instance and service key are the same as for the option [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md) \(when using clientId and clientsecret to call token server\).
> 
> `clientid` and `clientsecret` from the service key are directly used as credentials to authenticate the sender to call the integration flow.



<a name="loio647eeb3eca5d4c299009cacd1332247e__steps_ifg_1vy_cpb"/>

## Procedure

1.  Look up the role to be used to authorize the sender to call integration flow endpoint.

    This role is to be specified as *User Role* parameter for the corresponding sender adapter of the integration flow to be called.

    This can be either the standard role `ESBMessaging.send` or a custom role \(see [Managing User Roles](../50-Development/managing-user-roles-4e86f0d.md)\).

    To check out the roles defined for your tenant, go to the SAP Integration Suite *Monitor* section, and under *Manage Security*, select the *User Roles* tile.

2.  In SAP BTP cockpit, select the subaccount that hosts your SAP Integration Suite virtual environment and create a service instance and service key. However, during runtime, no access token is retrieved from the token server.

    Instead of an access token, the values of `clientid` and `clientsecret` from the service key are used as user credentials to access the integration flow endpoint.

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
    
    *integration-flow* 
    
    </td>
    <td valign="top">
    
    Keep standard role `ESBMessaging.send` or use one or more custom roles.
    
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
    
3.  Configure the sender system.

    Make sure that the sender keystore contains the root certificate of the load balancer server certificate.

    Get this certificate using the SAP Integration Suite *Connectivity Test* \(pointing to the integration flow endpoint address\). From downloaded`.zip` file, select the `*.cer` file of the root certificate and import this into the sender system keystore.

    More information: [Using the Connectivity Test to Get the Load Balancer Server Root Certificate](using-the-connectivity-test-to-get-the-load-balancer-server-root-certificate-5d6cbf4.md)

4.  Configure the inbound communication for the related integration flow.

    1.  Go to the SAP Integration Suite *Design* section and edit the relevant integration flow.

    2.  Create a sender channel with the adapter type that supports this authentication option, and select the connection for the associated sender adapter.

    3.  For *Authorization*, choose *User Role* and specify the role. Keep the role name *ESBmessaging.send* pre-entered by default in the *User Role*. You can also select a custom role if you want to use a dedicated role to control authorization to the process the integration flow.

    4.  After you have finished configuring the integration flow, including the processing steps for your scenario, deploy the integration flow on the tenant.

        To do this, save the integration flow and choose *Deploy*.



**Related Information**  


[Basic Authentication](basic-authentication-2c4c2d9.md "Basic authentication allows a client to authenticate itself against the server based on user credentials.")

[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/24585cc503334e6c917ef383efb5558a.html "") :arrow_upper_right:

