<!-- loio3b55fa7b83874b5ca3b6b6b5998a73f6 -->

# Creating an RFC Destination

Create an RFC destination by adding necessary properties before using it in the integration flow of RFC adapter.



## Context

> ### Note:  
> SAP System Identification \(SID\) code must be unique for RFC backend, see: SAP Note [1405466](https://launchpad.support.sap.com/#/notes/1405466).



## Procedure

1.  Log into the SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations*. For using the adapter in Edge Integration Cell runtime, choose *Destinations \(New\)*.

    > ### Note:  
    > Synchronization of the new destination from the BTP Cockpit to the Edge Integration Cell runtime typically takes two minutes.

3.  Choose *Create Destination*. In the *Destination Configuration* section, do use the *Blank Template* tab as *Service Instance* only applies for HTTP destinations. Choose *Save*.

    For Edge Integration Cell runtime, choose *Create* and then select:

    -   *From Scratch*: To add all the necessary details including target endpoint, type of proxy, authentication method, and credentials, etc.
    -   *From File*: To add a destination by providing a JSON, YAML, or properties file containing its properties.

    Choose *Create*.

4.  Enter the details for the parameters *<Name\>*, *<URL\>*, *<User\>*, *<Password\>*, and select *<Type\>* as *RFC*.

    > ### Note:  
    > -   For Cloud Integration runtime profile, setting up an RFC connectivity for ABAP environment using principal propagation. Select *OnPremise* from the value help and then for *<Authentication\>*, select *PrincipalPropagation*.
    > 
    > -   For using RFC adapter in Edge Integration Cell runtime, set *Proxy Type* as *<Local\>*.

5.  Add the following properties and assign appropriate values:

    **Java Connectivity Parameters**


    <table>
    <tr>
    <th valign="top">

    Parameters
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    **Connection Parameters**\(first four properties are mandatory\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.ashost
    
    </td>
    <td valign="top">
    
    The IP address or hostname of the SAP application server.

    > ### Note:  
    > For runtimes other than Edge Integration Cell, the value provided for application server host \(ashost\) property is the access control value created in the Cloud Connector.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.client
    
    </td>
    <td valign="top">
    
    The SAP client number.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.lang
    
    </td>
    <td valign="top">
    
    The language for communication with SAP SAP \(e.g., en for English\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.sysnr
    
    </td>
    <td valign="top">
    
    The system number of the SAP instance \(e.g., 27\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.user
    
    </td>
    <td valign="top">
    
    The SAP username for authentication
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.passwd
    
    </td>
    <td valign="top">
    
    The password for the SAP user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.destination.auth\_type
    
    </td>
    <td valign="top">
    
    While configuring for principal propagation the value for the property is "jco.destination.auth\_type = PrincipalPropagation".
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    **Connection Pool Parameters**
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    \(optional\) jco.destination.pool\_capacity
    
    </td>
    <td valign="top">
    
    The number of connections that are kept open in the connection pool for reuse.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    \(optional\) jco.destination.peak\_limit
    
    </td>
    <td valign="top">
    
    The maximum number of concurrent connections allowed at peak times.
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    WebSocket Connection
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.destination.auth\_type
    
    </td>
    <td valign="top">
    
    If you’re using principal propagation for authentication, for the property jco.destination.auth\_type, specify the value as PrincipalPropagation. Don’t specify any additional credentials in the destination.

    Location ID should correspond to the cloud connector name found in the master instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.client
    
    </td>
    <td valign="top">
    
    The SAP client number
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.tls\_trust\_all
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.wshost
    
    </td>
    <td valign="top">
    
    Host for websocket connection
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.wsport
    
    </td>
    <td valign="top">
    
    Port for websocket connection
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.destination.repository\_roundtrip\_optimization
    
    </td>
    <td valign="top">
    
    Set the value to 0 that helps you to minimizes the number of roundtrip calls made to the server
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    **[Set Up SNC on Edge Integration Cell](../60-Security/set-up-snc-on-edge-integration-cell-c2315d3.md) - Secure Network Communication \(SNC\)** parameters \(Set the following parameters \(mandatorily\) to use the RFC adapter Edge Integration Cell runtime\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.snc\_mode
    
    </td>
    <td valign="top">
    
    Set the value to 1 to enable SNC.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.snc\_partnername
    
    </td>
    <td valign="top">
    
    SNC partner name. The format for SNC partner names is *<p:<distinguished name\>*, where distinguished name comes from the public certificates of the trusted partners
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    jco.client.snc\_qop
    
    </td>
    <td valign="top">
    
    Protection levels for SNC, which ranges from 1 to 9, where 9 signifies the highest level of protection. By default, the value is 8.
    
    </td>
    </tr>
    </table>
    
6.  Verify and save the destination, and do a connection check.

    > ### Note:  
    > Synchronization of the new destination from the BTP Cockpit to the Edge Integration Cell runtime for the first time typically takes upto five minutes.


**Related Information**  


[Create RFC Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-rfc-destinations?version=Cloud)

[Managing Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/managing-destinations?version=Cloud)

