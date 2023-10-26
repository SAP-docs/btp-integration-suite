<!-- loio270f353a5b69472696617d91ceb58c93 -->

# Creating HTTP Destinations and Transport Route

Create destinations, transport nodes, and transport routes to configure the content transport landscape.



<a name="loio270f353a5b69472696617d91ceb58c93__prereq_x1k_zmr_gbb"/>

## Prerequisites

-   Enable the **Solutions Lifecycle Management** \(SLM\) service. For information, see [Enabling Content Transport, Neo Environment](enabling-content-transport-neo-environment-425db2b.md).

-   To use CTS+ as your transport option, complete the following steps:

    -   Set up CTS+ for the transport purpose. See [Activating and configuring CTS Export Web Service](https://help.sap.com/viewer/62938f21156047718cae23da55f2b443/latest/en-US/aa779d7c617143629a2c851f99eda4f1.html).

    -   Install and configure Cloud Connector to connect your on-premise system with SAP Cloud Integration. See [Cloud Connector](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/d751d065774e45e1b6bdbfdfd541da13.html).


-   To use Cloud Transport Management as your transport option, complete the initial setup. See [Cloud Transport Management Setup](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).




<a name="loio270f353a5b69472696617d91ceb58c93__context_mm4_m3d_qbb"/>

## Context

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

<a name="id_v3n_lyb_srb"/>

<!-- id\_v3n\_lyb\_srb -->

## HTTP Destinations and Transport Route



The steps involved in creating HTTP destinations and transport route are different for different transport modes. Choose a transport mode \(box\) to view the detailed procedure for creating destinations and transport routes.

The information within a transport mode is independent of other modes.

![](images/HTTP_Destinations_for_Transport_8f81529.png)



### 

**Creating HTTP Destinations for MTAR Download** 

1.  In the SAP BTP Neo subaccount where your source Cloud Integration tenant is hosted, choose *Services* \> *Solutions Lifecycle Management* \> *Configure Destinations*.

2.  Choose *New Destination* to create a destination targeted at the source Cloud Integration tenant.

    In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter the value `CloudIntegration`. This value is case-sensitive.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description \(optional\)
    
    </td>
    <td valign="top">
    
    You can provide a description for your reference.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Enter the URL of the source tenant \(access URL of Cloud Integration web UI\).

    URL format: *<https://<Cloud\_Integration\_tenant\_name\>-tmn.hci.int.<region\>.hana.ondemand.com/itspaces/\>*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Basic Authentication

    > ### Remember:  
    > The user must be a member of the source SAP Cloud Integration tenant. The user must also have the roles *AuthGroup.IntegrationDeveloper* and *IntegrationContent.Transport*. See [Configuring User Access to Cloud Integration](../InitialSetup/configuring-user-access-to-cloud-integration-ed6033b.md).


    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.


Your tenant is now ready to download MTAR files of the integration content that you want to transport.



### 

**Creating HTTP Destinations and Transport Route for CTS+**

Create 3 HTTP destinations – 2 in Solutions Lifecycle Management and 1 in CTS+ system. Also, create another destination to connect your CTS+ system with your Cloud Integration source tenant using Cloud Connector. Finally, configure transport nodes and route.

1.  Create destinations in Solution Lifecycle Management for your source and target Cloud Integration tenants:

    1.  In the SAP BTP Neo subaccount where your source Cloud Integration tenant is hosted, choose *Services* \> *Solutions Lifecycle Management* \> *Configure Destinations*.

    2.  Choose *New Destination* to create a destination targeted at the source Cloud Integration tenant.

        In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Enter the value `CloudIntegration`. This value is case-sensitive.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description \(optional\)
        
        </td>
        <td valign="top">
        
        You can provide a description for your reference.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Enter the URL of the source tenant \(access URL of Cloud Integration web UI\).

        URL format: *<https://<Cloud\_Integration\_tenant\_name\>-tmn.hci.int.<region\>.hana.ondemand.com/itspaces/\>*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Proxy Type
        
        </td>
        <td valign="top">
        
        Internet
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Basic Authentication

        > ### Remember:  
        > The user must be a member of the source Cloud Integration tenant. The user must also have the roles *AuthGroup.IntegrationDeveloper* and *IntegrationContent.Transport*. See [Configuring User Access to Cloud Integration](../InitialSetup/configuring-user-access-to-cloud-integration-ed6033b.md).


        
        </td>
        </tr>
        </table>
        
    3.  Choose *Save*.

    4.  Repeat the same steps in the subaccount where your target Cloud Integration tenant is hosted. Use the URL of the target tenant.


2.  Establish a connection between Cloud Integration and the CTS+ system:

    1.  Open the WSDL Generation document of your CTS web service. See [Displaying a WSDL Document](https://help.sap.com/viewer/684cffda9cbc4187ad7dad790b03b983/latest/en-US/8e78b295106a444784ea39bf050ed5de.html).

    2.  Copy the *WSDL URL for Binding* and launch it in a browser. In the WSDL response, search for `soap:address location`. Copy the location URL.

    3.  In SAP Cloud Connector, use the copied URL to allow Cloud Integration access the CTS+ system. See [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html) for the detailed steps.

    4.  In the SAP BTP Neo subaccount where your source Cloud Integration tenant is hosted, choose *Services* \> *Solutions Lifecycle Management* \> *Configure Destinations*.

    5.  Choose *New Destination* to create a destination targeted at the CTS+ system.

        In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Enter the value `TransportSystemCTS`. This value is case-sensitive.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description \(optional\)
        
        </td>
        <td valign="top">
        
        You can provide a description for your reference.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Enter the URL that you copied from the WSDL response.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Proxy Type
        
        </td>
        <td valign="top">
        
        OnPremise
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Basic Authentication
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Additional Properties* 
        
        </td>
        <td valign="top">
        
        Choose *New Property*.

        Enter `sourceSystemId` as the key and provide a value of your choice. Reuse the same value as the name of the source non-ABAP system in a later step.
        
        </td>
        </tr>
        </table>
        

3.  Create a destination in CTS+ system for the target Cloud Integration tenant:

    1.  In your CTS Communication system, enter the transaction code `SM59` to open the RFC Destinations.

    2.  Enable the checkbox for *HTTP Connections to External Server* and choose *create*.

    3.  In the RFC Destination creation page, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *RFC Destination* 
        
        </td>
        <td valign="top">
        
        Enter a name for the destination. You use the name in a later step.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Technical Settings* 
        
        </td>
        <td valign="top">
        
        -   *Target Host*: Enter the host name of the SLM service endpoint \(of the SAP BTP Neo subaccount where your source Cloud Integration tenant is hosted\).

            The host name must be in the format: *<slservice.<landscape-host\>*

        -   *Path Prefix*: Enter the path prefix, which must be in the format *</slservice/slp/basic/<Technical Name of the Neo subaccount\>/slp\>*.

        -   *HTTP Proxy Options*: Configure a proxy for HTTP connections. You can determine the proxy host and service, as well as users and passwords for the HTTP connection.



        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Logon & Security* 
        
        </td>
        <td valign="top">
        
        -   Choose *Basic Authentication*. Provide the credentials of the user who is a member of the target Cloud Integration tenant.

        -   For *SSL* options, choose *Active*.



        
        </td>
        </tr>
        </table>
        
    4.  Choose *Save*.

    5.  Choose *Connection Test* to check if the connection was successfully established.


    For more information about creating a destination in SM59, refer to [Establishing a Connection Using a Destination \(SM59\)](https://help.sap.com/viewer/753088fc00704d0a80e7fbd6803c8adb/latest/en-US/48d7ad896b57154ee10000000a421937.html).

4.  Configure SAP BTP as an application type in CTS+ system:

    1.  In your CTS Communication system, enter the transaction code `STMS` to open the Transport Management System.

    2.  Choose *System Overview*.

    3.  Choose *Extras* \> *Application Types* \> *Configure* and then choose *New Entries*.

    4.  For the *Application ID*, provide the value `HCP` and an optional description.

    5.  Choose *Save*.


5.  Configure the transport nodes:

    1.  In your CTS Communication system, enter the transaction code `STMS`.

    2.  Choose *System Overview*.

    3.  Configure the non-ABAP systems \(source and target Cloud Integration tenants\) .

        1.  Using the steps mentioned in [Defining and Configuring Non-ABAP Systems](https://help.sap.com/viewer/05c12df5b54849c49940a14bc089d8b4/latest/en-US/bfe4626214504be18b2f1abeeaf4f8e4.html), configure the source and target systems.

            > ### Note:  
            > -   The application ID for the source system must be the same as the property you defined in [Additional Properties](creating-http-destinations-and-transport-route-270f353.md#loio270f353a5b69472696617d91ceb58c93__addl-prop1).
            > 
            > -   For the target system configuration, choose *Other* as the deployment method.

        2.  Using the steps mentioned in [Configuring Target Systems for Further Applications](https://help.sap.com/viewer/05c12df5b54849c49940a14bc089d8b4/latest/en-US/52700dbe608e4752a8e2e96a1876f865.html), connect the target tenant with CTS+ system.

            -   For *Deploy method*: choose `HTTP-based Deployment (application-specific)`.

            -   For *HTTP destination*: choose the [RFC destination](creating-http-destinations-and-transport-route-270f353.md#loio270f353a5b69472696617d91ceb58c93__RFC_dest) that you created.




6.  Configure the transport route:

    1.  Enter the transaction code `STMS` to open the Transport Management System.

    2.  Choose *Transport Routes*. Switch to edit mode by choosing *Display ↔ Change*.

    3.  Choose *Edit* \> *Transport Layer* \> *Create*.

    4.  Enter a name and an optional description. Choose *Transfer* to create the transport layer.

    5.  Choose *Edit* \> *Transport Route* \> *Add Transport Route*.

    6.  Using the pencil icon, draw a line from your source system to target system.

    7.  In the *Create Transport Route* dialog, choose *Consolidation*. In the *Transport Layer* field, enter the name of the transport layer that you created.

    8.  Choose *Transfer* to save the transport route.

    9.  Choose *Distribute and Activate*.





### 

**Creating HTTP Destinations for Cloud Transport Management**

Create 4 HTTP destinations – 2 in Solutions Lifecycle Management, 1 each in SAP BTP Neo and Cloud Foundry subaccounts. Later, create transport nodes and route.

1.  Create destinations in Solution Lifecycle Management for your source and target Cloud Integration tenants:

    1.  In the SAP BTP Neo subaccount where your source Cloud Integration tenant is hosted, choose *Services* \> *Solutions Lifecycle Management* \> *Configure Destinations*.

    2.  Choose *New Destination* to create a destination targeted at the source Cloud Integration tenant.

    3.  In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Enter the value `CloudIntegration`. This value is case-sensitive.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description \(optional\)
        
        </td>
        <td valign="top">
        
        You can provide a description for your reference.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Enter the URL of the source tenant \(access URL of Cloud Integration web UI\).

        URL format: *<https://<Cloud\_Integration\_tenant\_name\>-tmn.hci.int.<region\>.hana.ondemand.com/itspaces/\>*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Proxy Type
        
        </td>
        <td valign="top">
        
        Internet
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Basic Authentication

        > ### Remember:  
        > The user must be a member of the source Cloud Integration tenant. The user must also have the roles *AuthGroup.IntegrationDeveloper* and *IntegrationContent.Transport*. See [Configuring User Access to Cloud Integration](../InitialSetup/configuring-user-access-to-cloud-integration-ed6033b.md).


        
        </td>
        </tr>
        </table>
        
    4.  Choose *Save*.

    5.  Repeat the same steps in the subaccount where your target Cloud Integration tenant is hosted. Use the URL of the target tenant.


2.  Create a destination in your SAP BTP Neo subaccount for Cloud Transport Management service:

    1.  In the SAP BTP subaccount where your source Cloud Integration tenant is hosted, create a destination targeted at the Cloud Transport Management service.

        In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Enter the value `TransportManagementService`. This value is case-sensitive.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description \(optional\)
        
        </td>
        <td valign="top">
        
        You can provide a description for your reference.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Enter the value of `uri` from the service key of your Cloud Transport Management instance.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Proxy Type
        
        </td>
        <td valign="top">
        
        Internet
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        OAuth2ClientCredentials
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client ID
        
        </td>
        <td valign="top">
        
        Enter the value of `clientid` from the service key of your Cloud Transport Management instance.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client Secret
        
        </td>
        <td valign="top">
        
        Enter the value of `clientsecret` from the service key of your Cloud Transport Management instance.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Token Service URL
        
        </td>
        <td valign="top">
        
        Enter the value of `url` from the service key of your Cloud Transport Management instance. Append `/oauth/token` at the end of URL fetched from the service key.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Additional Properties* 
        
        </td>
        <td valign="top">
        
        Choose *New Property*.

        Enter `sourceSystemId` as the key and provide a value of your choice. Reuse the same value as the name of the source transport node in a later step.
        
        </td>
        </tr>
        </table>
        

3.  Create a destination in your SAP BTP Cloud Foundry subaccount:

    1.  In your SAP BTP Cloud Foundry subaccount \(where you've subscribed to Cloud Transport Management service\), choose *Connectivity* \> *Destinations*.

    2.  Choose *New Destination* to create a destination targeted at the SAP BTP Neo subaccount where your target Cloud Integration tenant is hosted.

        In the *Destination Configuration* section, enter values in fields based on the description provided in the following table.


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Provide a name for the destination.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description \(optional\)
        
        </td>
        <td valign="top">
        
        You can provide a description for your reference.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Enter the URL of the SLM service endpoint in the target subaccount.

        URL format: *<https://slservice.<landscape-host\>/slservice/slp/basic/<Technical Name of the Neo subaccount\>/slp\>*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Proxy Type
        
        </td>
        <td valign="top">
        
        Internet
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Basic Authentication

        > ### Remember:  
        > The user must be a member of the target Cloud Integration tenant.


        
        </td>
        </tr>
        </table>
        
        You've created the necessary destinations. The next steps are to create transport nodes and routes.


4.  In Cloud Transport Management service, create the source and target transport nodes. The name for the source node must be the same as the property you defined in [Additional Properties](creating-http-destinations-and-transport-route-270f353.md#loio270f353a5b69472696617d91ceb58c93__addl-prop2) of the destination in Solution Lifecycle Management for Cloud Transport Management service. See: [Create Transport Nodes](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/f71a4d5550cd453ea824d5b5c677969d.html).

5.  In Cloud Transport Management service, create a transport route using the preceding nodes. See: [Create Transport Routes](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/dddb74937a014aea8d3d76d740180597.html).


