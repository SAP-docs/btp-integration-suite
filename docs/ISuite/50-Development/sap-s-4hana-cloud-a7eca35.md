<!-- loioa7eca35b7f544207833bd87f44f69dd1 -->

# SAP S/4HANA Cloud

As an administrator of an SAP S/4HANA Cloud configured IAS tenant you need to configure the communication between Graph and SAP S/4HANA Cloud.

To do this, you need to set up the connectivity on the SAP S/4HANA Cloud tenant and on the SAP BTP tenant for SAP Cloud Identity Access Governance \(IAG\), and create destinations.



<a name="loioa7eca35b7f544207833bd87f44f69dd1__section_czl_pj2_5xb"/>

## Set Up Connectivity



### Prerequisites

The SAP S/4HANA Cloud administrator must have the following business role assignments:


<table>
<tr>
<th valign="top">

Business Role ID

</th>
<th valign="top">

Area

</th>
</tr>
<tr>
<td valign="top">

SAP\_BCR\_CORE\_COM

</td>
<td valign="top">

Communication Management

</td>
</tr>
<tr>
<td valign="top">

SAP\_BCR\_CORE\_IAM

</td>
<td valign="top">

Identity and Access Management

</td>
</tr>
<tr>
<td valign="top">

SAP\_BCR\_CORE\_EXT

</td>
<td valign="top">

Extensibility

</td>
</tr>
</table>



### Procedure

1.  Configure the single-sign on \(SSO\) Identity Authentication service.
2.  Upload your key-pair keystore in SAP BTP cockpit. Otherwise, use the default key-pair keystore.

3.  Set up the SAP S/4HANA Cloud side.
4.  Set up the SAP BTP side.

For a detailed description of each of these steps, see [Using SAML Bearer Assertion Authentication](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f9d5adca9e414d9b8c42513a8890d782.html).



### Handover Information to the SAP BTP Administrator

-   URL of your SAP S/4HANA Cloud account
-   Name of the communication user in the SAP S/4HANA Cloud tenant
-   Password for the communication user
-   Token Service URL from the OAuth 2.0 details in the communication arrangement
-   Provider name for the communication system in SAP S/4HANA Cloud



<a name="loioa7eca35b7f544207833bd87f44f69dd1__section_tvq_3k2_5xb"/>

## Create Destinations

Create a destination to enable the communication between your business system and Graph.

You can define destinations to data sources using two authentication models: identity propagation \(preferred\) and based on a technical user. Both options are described here for each supported business system.

> ### Note:  
> Graph caches destination settings. If you want to change these settings after the business data graph is created, you need to edit the business data graph configuration and update it. For more information, see [Modify Your Business Data Graph](modify-your-business-data-graph-0084c4d.md).

As the SAP BTP administrator, you must create and configure an HTTP destination that either supports principal propagation or is based on a technical user.

> ### Note:  
> An HTTP destination can be generated automatically by extending SAP S/4HANA Cloud in the Cloud Foundry and Kyma environments. For more information, follow the steps in:
> 
> -   [Extending SAP Solutions Using Automated Configurations](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/346864df64f24011b49abee07bbd79af.html)
> 
> -   [Extending SAP S/4HANA Cloud in the Cloud Foundry and Kyma Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/40b9e6c3cc43498b92472da13e88c7bf.html).



### Destination for Identity Propagation

**Prerequisites**

The SAP S/4HANA Cloud Administrator configured the communication between Graph and SAP S/4HANA Cloud. You know the following:

-   URL of your SAP S/4HANA Cloud account

-   Name of the communication user in the SAP S/4HANA Cloud tenant

-   Password for the communication user

-   Token Service URL from the OAuth 2.0 details in the communication arrangement

-   Provider name for the communication system in SAP S/4HANA Cloud


For more information, see [Principal Propogation Scenario: Cloud to Cloud](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/scenario-cloud-to-cloud).

**Procedure**

Create an *OAuth2SAMLBearerAssertion* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit *Connectivity* \> *Destinations* and choose *New Destination*. Enter the following:


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
    
    Enter the destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    `HTTP` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The service URL from the communication arrangement.

    > ### Note:  
    > Make sure you use the HTTPS protocol.


    
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
    
    OAuth2SAMLBearerAssertion
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Store Location
    
    </td>
    <td valign="top">
    
    In the dropdown list, select the key-pair keystore file you uploaded in [Upload Your Key-Pair Keystore in SAP BTP](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f9d5adca9e414d9b8c42513a8890d782.html#loio1c58ebce86514260a3b5be9fb9587745).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Store Password
    
    </td>
    <td valign="top">
    
    The password for the keystore.

    > ### Note:  
    > The password for the keystore must be the same as the one for the key-pair entry in the keystore file.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    The URL of your SAP S/4HANA Cloud account. To get it, log on to your SAP S/4HANA Cloud account. Select the profile picture, choose *Settings*, and copy the value from the *Server* field. Add `https://` to the beginning of the URL.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    The name of the communication user you have in the SAP S/4HANA Cloud tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    The token service URL from the OAuth 2.0 details in the communication arrangement.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL Type
    
    </td>
    <td valign="top">
    
    Dedicated
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service User
    
    </td>
    <td valign="top">
    
    The name of the communication user in the SAP S/4HANA Cloud tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service Password
    
    </td>
    <td valign="top">
    
    The password for the communication user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    System User
    
    </td>
    <td valign="top">
    
    Leave the field empty.
    
    </td>
    </tr>
    </table>
    
2.  Configure the required additional properties. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following parameters:


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
    
    `authnContextClassRef`
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:2.0:ac:classes:X509`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `nameIdFormat`
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `scope`
    
    </td>
    <td valign="top">
    
    For example: `API_BUSINESS_PARTNER_0001`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `userIdSource`
    
    </td>
    <td valign="top">
    
    email
    
    </td>
    </tr>
    </table>
    
3.  Select the *Use default JDK truststore* checkbox.

4.  Click *Save*.




### Destination with a Technical User

**Prerequisites**

The SAP S/4HANA Cloud administrator configured the communication between Graph and SAP S/4HANA Cloud. You know the following:

-   URL of your SAP S/4HANA Cloud account

-   Name of the communication \(technical\) user in the SAP S/4HANA Cloud tenant

-   Password for the communication user


**Procedure**

Create a *BasicAuthentication* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit *Connectivity* \> *Destinations* and choose *New Destination*. Enter the following:


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
    
    Enter a destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    `HTTP` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The service URL from the communication arrangement.

    > ### Note:  
    > Make sure you use the HTTPS protocol.


    
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
    
    `BasicAuthentication` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    The name of the communication user in the SAP S/4HANA Cloud tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    The password for the communication user.
    
    </td>
    </tr>
    </table>
    
2.  Click *Save*.


