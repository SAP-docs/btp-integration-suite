<!-- loio0804b498d3a4411c91eafe5410825164 -->

# Create a Destination for Approving and Rejecting Subscriptions

Create a destination in the SAP BTP Cockpit that contains the contains the connectivity details of the Service Provider Interface \(SPI\) implementation. This destination allows Developer Hub to forward subscription requests for external governance processing.



<a name="loio0804b498d3a4411c91eafe5410825164__steps_nv2_z2d_44b"/>

## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  Choose the *Connectivity* \> *Destinations* tab in the left-hand pane.

3.  Choose *Create* and in the *Create New Destination* popup, select *From Scratch* to create a new destination manually.

4.  In *Destination Details* section, fill in all the required details according to the descriptions provided in the table.

    > ### Note:  
    > Use the credentials provided by the customer sub-account administrator. Supported authentication methods include *OAuth 2.0*, *Client Certificate*, and *Basic* authentication.


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
    
    Enter `DeveloperHub_Governance_SPI` as the destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Enter `HTTP` as the supported type.
    
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
    
    Enter the customer governance application URL.
    
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
    
    Select the authentication type depending on your requirement.

    -   Basic: User provides a simple *Username* and *Password* based authentication.
    -   Client Certificate: The user provides the *Key Store Source*, *Key Store Location*, and *Key Store Password*. The server verifies the certificate to grant access.
    -   OAuth2ClientCredentials: Used when third-party services need to access resources without sharing the user’s password. A backend service authenticating with a resource server to access an API using *Client ID*, *Client Secret*, and *Token Service URL*. The token URL should correspond to the customer governance application when OAuth2 is being used.


    
    </td>
    </tr>
    </table>
    
5.  Choose *Create*.

    You can also do a *Check Connection* to verify whether you've added the destination correctly.




<a name="loio0804b498d3a4411c91eafe5410825164__result_j2v_h2w_n4b"/>

## Results

You’ve created the destination *DeveloperHub\_Governance\_SPI*.

