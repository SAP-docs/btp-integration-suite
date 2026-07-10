<!-- loio37e70f468cc74a11985e6f38d0726639 -->

# Configure a BTP Destination for API Invocation of a Discovered API \(On-Premise\)

After discovering APIs using the **on-premise** SAP Gateway destination, select a destination for making runtime calls for the API artifact. You can reuse the same destination used for discovery.



## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  From the left navigation pane, choose *Connectivity* \> *Destinations*.

3.  Choose *Create*. The *Create New Destination* window appears.

4.  Choose *From Scratch* to create a new destination manually.

5.  In the *Destination Details* section, enter all the required information as described in the table below:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Provide a unique name for the destination.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Choose *HTTP* as the supported type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Choose *OnPremise* as the supported proxy type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description \(optional\)
    
    </td>
    <td valign="top">
    
    Enter a brief description stating the purpose of creating a new destination in the *Description* field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Enter the URL of the backend SAP Gateway system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Cloud Connector Location ID
    
    </td>
    <td valign="top">
    
    If you have configured multiple cloud connectors to your SAP BTP account, then provide the location ID of the cloud connector that you want to add.

    The *Location ID* value for a cloud connector is set while adding a subaccount in cloud connector.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select the authentication method to be used for connection requests to the server.

    Supported authentication mechanisms includes:

    -   Basic Auth
    -   No Auth
    -   OAuth2ClientCredentials
    -   OAuth2Password


    
    </td>
    </tr>
    </table>
    
    Scroll down to the *Labels* section, choose *Add* and add the following label:*IntegrationCell.Include*and set its value to *true*.


