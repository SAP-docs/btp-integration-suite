<!-- loio9bb2c8a813da436bbe82d245056a79ce -->

# Configure a BTP Destination for API Discovery from an SAP Gateway System \(Internet-Based\)

To create an API artifact by discovering your SAP cloud backends through an **internet-based** SAP Gateway service, you must first configure your gateway system details as a BTP destination. This destination is then available under Discoverable Systems during the API provider creation flow.



## Context

To enable API discovery:

-   Create a destination in the SAP BTP cockpit pointing to the internet-accessible SAP Gateway host.

-   Maintain the required authentication configuration.

-   Provide the correct host URL and connection details.

-   This destination allows SAP to connect to your backend systems via the gateway service and retrieve the backend APIs available for discovery.




## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

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
    
    Choose *Internet* as the supported proxy type.
    
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
    
    Enter the base/host URL of the backend SAP Gateway system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select the authentication method to be used for connection requests to the server.

    For Internet-type gateway systems, only *Basic Auth* is supported.
    
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
    
    Specify the relative path from where the catalog service should be fetched. For example: `/iwfnd/catalogservice/ServiceCollection` 
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The base URL, pathPrefix, and serviceCollectionUrl are concatenated to form the final Catalog Service URL.

    Scroll down to the *Labels* section, choose *Add* and add the following labels:

    -   *IntegrationCell.Include*and set its value to *true*
    -   *systemType*and set its value to *gateway*

    .


