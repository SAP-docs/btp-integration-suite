<!-- loio7e84b0e0e0a7478c99900168bb222add -->

# Configure a BTP Destination for API Discovery from an SAP Gateway System \(On-Premise\)

After you have discovered the list of APIs via the Gateway service destination, configure a destination with the **Proxy Type** set to **OnPremise** to make the runtime calls for the created API artifact. You can also reuse the same destination that was used for API discovery.



## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  From the left navigation pane, choose *Connectivity* \> *Destinations*.

3.  Choose *Create*. The *Create New Destination* window appears.

4.  Choose *From Scratch* to create a new destinationation manually.

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
    
    Enter the URL of your backend systems.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Cloud Connector Location ID
    
    </td>
    <td valign="top">
    
    If you have configured multiple cloud connectors to your SAP BTP account, then provide the location ID of the cloud connector that you want to add.

    The *Location ID* value for a cloud connector is set while adding a sub-account in cloud connector.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select the authentication method to be used for connection requests to the server.

    For On-premise type gateway systems, only Basic Authentication is supported.
    
    </td>
    </tr>
    </table>
    
    In the *Additional Properties* section, choose *Add Property* and provide the following values:

    ****


    <table>
    <tr>
    <th valign="top">

    Additional Properties
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    pathPrefix
    
    </td>
    <td valign="top">
    
    Enter the prefix path for your SAP Gateway endpoint.

    Example: `/sap/opu/odata`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    serviceCollectionUrl
    
    </td>
    <td valign="top">
    
    Specify the relative path from where the catalog service should be fetched. For example:`/iwfnd/catalogservice/ServiceCollection` 
    
    </td>
    </tr>
    </table>
    
    Scroll do

    > ### Note:  
    > The base URL, pathPrefix, and serviceCollectionUrl are concatenated to form the final Catalog Service URL.

    wn to the *Labels* section, choose *Add* and add the following labels:

    -   *IntegrationCell.Include*and set its value to *true*
    -   *systemType*and set its value to *gateway*

    .


