<!-- loio6b263e2c1b2d4d9ba20bcd7872eedd9e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an API Provider

Define the details of the host you want an application to reach by creating an API provider.



<a name="loio6b263e2c1b2d4d9ba20bcd7872eedd9e__prereq_z3k_mnq_pgb"/>

## Prerequisites

-   You’re assigned the `APIPortal.Administrator` role.

-   For *Open Connectors* type provider, fetch the *Organization Secret*and *User Secret* from the Open Connectors page.

    > ### Note:  
    > Open Connectors is now a part of SAP Integration Suite. To activate the capability, choose *Add Capabilities* and choose *Extend Non-SAP Connectivity* in the *Activate Capabilities* screen. For more information, see [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?state=DRAFT&version=CLOUD) and [Configuring User Access](https://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?state=DRAFT&version=CLOUD&q=the%20Organization%20Secret%20and%20User%20Secret). Once the capability is activated, navigate back to the home page and choose the :pencil2: icon on the *Extend Non-SAP Connectivity* tile. On the *Integration Suite Open Connectors* page, choose the :gear: icon at the bottom left of the screen and note down the *Organization Secret*and *User Secret*.
    > 
    > You’re navigated to *Integration Suite* homepage. At first, you have to activate the Open Connectors capability.

-   The following prerequisites are applicable for *On-Premise* type provider only.
    1.  Expose the on-premise system using *Cloud Connector*. For more details, see [here](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html).
    2.  From your *Subaccount*, choose *Cloud Connectors* from the left-hand pane and validate if the system exposed in the previous step is visible in the list.




<a name="loio6b263e2c1b2d4d9ba20bcd7872eedd9e__context_v2l_3cn_fdb"/>

## Context

If you want to configure the API Management solution to access data from a server that offers a specific service, for example, SAP Gateway service, SAP HANA, SAP Process Integration/Process Orchestration, SAP S/4HANA, or any 3rd party cloud solutions, we recommend configuring the solution as an API provider in the connection parameters. The Integration Suite enables you to configure connections to OData-hosted systems.

> ### Note:  
> You can see the following tutorial for visual instructions on how to [Create an API Provider System](https://developers.sap.com/tutorials/hcp-apim-create-provider.html).



<a name="loio6b263e2c1b2d4d9ba20bcd7872eedd9e__steps_w2l_3cn_fdb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

    The lists of API providers appear.

3.  Choose *Create*.

4.  Enter a name and a description for the API provider.

    > ### Note:  
    > Do not use the names mentioned in following list:
    > 
    > • DEST\_CI
    > 
    > • APIMGMT\_PORTAL
    > 
    > • ContentCatalog
    > 
    > • ON\_PREM
    > 
    > • Apimgmt\_rt
    > 
    > • Apimgmt\_rt\*
    > 
    > • TC
    > 
    > • TC\_\*

5.  Go to the *CONNECTION* section, enter the required details based on the type of connection you selected.

    -   Choose *Internet* to connect to a system on Cloud.
    -   Choose *On Premise* to connect to the on-premisnee system through Cloud Connector.
    -   Choose *Open Connectors* to connect third-party APIs via harmonized RESTful APIs.
    -   Choose *Cloud Integration* to access all the service endpoints.

    -   *Internet* connection type:

        **Internet**


        <table>
        <tr>
        <th valign="top">

        Field Name
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Host
        
        </td>
        <td valign="top">
        
        Enter a value for the host in the format "example.com".
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Port
        
        </td>
        <td valign="top">
        
        Enter 443 as the port number for SSL and 8080 for all other ports.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Use SSL
        
        </td>
        <td valign="top">
        
        Select the checkbox to secure the connection using SSL \(HTTPS protocol\).

        > ### Note:  
        > Setting this option is sufficient to set up the SSL connection. If you want to use SSL to secure connections to the configured destination, then upload the server certificate in the SAP BTP cockpit.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Trust store certificate
        
        </td>
        <td valign="top">
        
        By default, API Management trusts all TLS certificates. To validate a certificate, create a truststore to configure API Management to validate the certificate. Specify the trust store certificate details in the API provider.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Key store certificate
        
        </td>
        <td valign="top">
        
        Specify the key store certificate details.
        
        </td>
        </tr>
        </table>
        
    -   *On Premise* connection type:


        <table>
        <tr>
        <th valign="top">

        Field Name
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Host
        
        </td>
        <td valign="top">
        
        Enter a value for the host in the format "example.com". Ensure that you provide the cloud connecter virtual host.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Port
        
        </td>
        <td valign="top">
        
        Enter the port number exposed in the *Cloud Connector* as per the host.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Location ID
        
        </td>
        <td valign="top">
        
        If you have configured multiple cloud connectors to your SAP BTP account, then provide the location ID of the cloud connector that you want to add.

        > ### Note:  
        > The *Location ID* value for a cloud connector is set while configuring the cloud connector.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Choose an authentication method:

        -   *None*: No Authentication. This is a pass through flow and validation is initiated at the Integration Suite layer.
        -   *Principal Propagation*: Enables authentication of a message in the receiver system with the same user that issued the message in the corresponding sender system. For more details, see [Principal Propagation](principal-propagation-e2f3313.md).


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Additional Property
        
        </td>
        <td valign="top">
        
        Select *sap-client* from the dropdown and enter the three-digit client ID. Client-specific data is identified with the client identifier. SAP-client configured in API provider has the highest precedence for runtime calls, metadata fetch, and discovery.

        > ### Note:  
        > The metadata is fetched from the specified client ID.


        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > Adding trust-store and key-store certificates isn’t supported for the on-premise system.

    -   *Open Connectors* connection type:

        **Open Connectors**


        <table>
        <tr>
        <th valign="top">

        Field Name
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Region
        
        </td>
        <td valign="top">
        
        Select a region from the dropdown list.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Host
        
        </td>
        <td valign="top">
        
        Value is auto populated based on the selected region.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Port
        
        </td>
        <td valign="top">
        
        Value is auto populated.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Organization Secret
        
        </td>
        <td valign="top">
        
        Enter the organization secret. For more information on how to obtain the value, see prerequisites section.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        User Secret
        
        </td>
        <td valign="top">
        
        Enter the user secret. For more information on how to obtain the value, see prerequisites section.
        
        </td>
        </tr>
        </table>
        
    -   *Cloud Integration* connection type:

        **SAP Cloud Integration**


        <table>
        <tr>
        <th valign="top">

        Field Name
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Cloud Integration Host
        
        </td>
        <td valign="top">
        
        Enter a tenant-specific address of the Cloud Integration system which can be accessed to by a dialog user \(for example, an integration developer using the Web UI\) or through the OData API.

        Address of Web UI: https://<Cloud Integration Host\>/itspaces.

        Address of Cloud Integration OData API: https://<Cloud Integration Host\>/api/v1.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Port
        
        </td>
        <td valign="top">
        
        443 \(Default value\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        The authentication type can be:

        -   *Basic* for connecting requests to server. This Basic authentication requires you to enter a username and password.

        -   *OAuth2ClientCredentials* for connecting requests to the server.

            The OAuth2ClientCredentials authentication needs you to provide the following details:

            -   Client ID
            -   Client Secret
            -   Token URL

            > ### Note:  
            > The values you provide for the above, are the ones associated with your Cloud Integration tenant.



        
        </td>
        </tr>
        </table>
        
        Also see:

        -   [Setting Up OAuth for Cloud Integration in Cloud Foundry](setting-up-oauth-for-cloud-integration-in-cloud-foundry-641c56b.md)


6.  In the *CATALOG SERVICE SETTINGS* section, enter the required details.

    **Catalog Service Settings**


    <table>
    <tr>
    <th valign="top">

    Field Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Path Prefix
    
    </td>
    <td valign="top">
    
    Specify the path prefix.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Collection URL
    
    </td>
    <td valign="top">
    
    Specify the relative path from where the catalog service should be fetched. For example, `/CATALOGSERVICE/ServiceCollection`.

    > ### Note:  
    > The option is only relevant for SAP Gateway-enabled SAP NetWeaver systems. A catalog service retrieves a list of all available OData services on SAP Gateway. It’s based on a catalog service pattern proposed by Microsoft and consists of an implementation approach of the catalog service pattern in the context of SAP Gateway. Only use the field if you want to fetch services from SAP Gateway. For more information on the catalog service, see [here](http://help.sap.com/saphelp_gateway20sp10/helpdata/en/26/50ea3c3ceb44b0a437fa44c420ad49/content.htm).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Catalog URL
    
    </td>
    <td valign="top">
    
    Automatically populates the complete URL in the format https:<`host`\>:<`port`\>/<`path prefix`\>/Catalog Service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select the authentication method to be used for connection requests to the server. By default, the authentication type is set to *None*. If you choose *Basic*, then provide a user name and password as authentication credentials in the respective fields.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Catalog service settings aren’t applicable for Open Connectors type connection and SAP Cloud Integration.

7.  Save the changes.

    Choose*Configure* \> *API Provider* to view the newly created API provider. Further, you can test the connection of the API provider, by navigating to the API provider's details page and selecting *Test Connection*.

    > ### Note:  
    > The following table lists the attributes considered for testing the connection:
    > 
    > **Test Connection**
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Type
    > 
    > </th>
    > <th valign="top">
    > 
    > Supported Attributes
    > 
    > </th>
    > <th valign="top">
    > 
    > Unsupported Attributes
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Internet
    > 
    > </td>
    > <td valign="top">
    > 
    > -   *Connection* attributes
    >     -   Host
    >     -   Port
    >     -   UseSSL
    > 
    > -   *Catalog Service Settings* attributes
    >     -   Path Prefix \(if available\)
    >     -   Service Collection URL \(if available\)
    >     -   Trust All
    >     -   Authentication Type
    > 
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > -   *Connection* attributes
    >     -   Trust Store
    >     -   Key Store Certificate
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>
    > 
    > A fixed socket timeout of 5 seconds and connection timeout of 3 seconds is added to the http client, which makes the HEAD call to the API provider.


