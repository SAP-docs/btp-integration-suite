<!-- loiocf493ed9432c4779b56c824bc4de8916 -->

# Create a Destination to Connect Advanced Event Mesh with Developer Hub

Create a destination to establish a connection between Advanced Event Mesh and Developer Hub.



## Context

A destination is required to discover and publish events from Advanced Event Mesh on Developer Hub.

To create a destination, perform the steps below:



<a name="loiocf493ed9432c4779b56c824bc4de8916__steps_sjc_myq_khc"/>

## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  From the left navigation pane, choose *Connectivity* \> *Destinations*.

3.  Choose *Create*. The *Create New Destination* window appears.

4.  Choose *From Scratch* to create a new destination manually.

5.  In the *Destination Details* section, enter all required information as described in the table below:


    <table>
    <tr>
    <th valign="top">

    Fields
    
    </th>
    <th valign="top">

    Details
    
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
    
    Choose `HTTP` as the supported type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
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
    
    Enter the home page/ base URL of the Advanced Event Mesh portal.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Choose *BasicAuthentication*. The user provides a simple Username and Password based authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    Enter the username of the technical user. For example, you can use your email address.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    Use the token generated from the Advanced Event Mesh portal as the password.

    To generate the token, see [Creating an API Token](https://help.pubsub.em.services.cloud.sap/Cloud/ght_api_tokens.htm#Create).

    > ### Note:  
    > Please ensure the following permissions are added while creating the token:
    > 
    > -   *Read any Application Domain* \> *application\_domain:get:\**
    > 
    > -   *Do anything to any Event API* \> *event\_api:\*:\**
    > 
    > -   *Access to Event Portal Designer* \> *event\_designer:access* 


    
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
    
    Additional Property
    
    </td>
    <td valign="top">
    
    Choose *Add Property* and provide the following values:

    -   Key: `sap.isuite.dh.aem.enabled`

    -   Value: true



    
    </td>
    </tr>
    </table>
    
6.  Choose *Create*.

    You can also do a *Check Connection* to verify whether you've added the destination correctly.


