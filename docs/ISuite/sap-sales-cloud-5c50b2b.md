<!-- copy5c50b2bfb97749cca202943756de92bc -->

# SAP Sales Cloud

As an administrator for SAP Sales Cloud, you need to establish trust with the SAP BTP subaccount and create destinations..

You can use the SAML Bearer assertion flow for consuming OAuth-protected resources. Users are authenticated by using SAML against the configured trusted identity providers. The SAML assertion is then used to request an access token from an OAuth authorization server.

This access token must be added as an Authorization header with the value `Bearer <access-token>` in all HTTP requests to the OAuth-protected resources.



<a name="copy5c50b2bfb97749cca202943756de92bc__OAuth_SalesCloud"/>

## Configure the OAuth Identity Provider in SAP Sales Cloud

As the SAP Sales Cloud administrator, you must add the SAP BTP service provider as a trusted OAuth identity provider.

For more information, see [Configure OAuth Identity Provider in SAP Sales Cloud](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/40d20a26f3dd445facff151b249fcf94.html).



### Prerequisites from SAP BTP administrator

-   Trust certificate
-   Region host
-   Subaccount ID



### Procedure

Create an *OAuth2SAMLBearerAssertion* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit*Connectivity* \> *Destinations* and choose *New Destination*. Enter the following:


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
    
    Enter the destination name
    
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
    > The password for the keystore must be the same as the one for the key pair entry in the keystore file.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    The URL of your SAP Sales Cloud account. To get the URL, log on to your SAP Sales Cloud account. Select the profile picture and then choose *Settings* and copy the value from the *Server* field. Add `https://` to the beginning of the URL.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    The name of your communication user in the SAP Sales Cloud tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    This is the Token service URL from the OAuth 2.0 Details in the communication arrangement.
    
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
    
    The name of the communication user in the SAP Sales Cloud tenant.
    
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
    
    This parameter is not used, leave the field empty.
    
    </td>
    </tr>
    </table>
    
2.  Configure the required additional properties. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following:


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
    
    authnContextClassRef
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:2.0:ac:classes:X509`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    nameIdFormat
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    scope
    
    </td>
    <td valign="top">
    
    For example: `API_BUSINESS_PARTNER_0001`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    userIdSource
    
    </td>
    <td valign="top">
    
    `email`
    
    </td>
    </tr>
    </table>
    
3.  Select the *Use default JDK truststore* checkbox.

4.  Click *Save*.




## Configure the OAuth Client for OData Access

As the SAP Sales Cloud administrator, you must configure the OAuth client for OData access to SAP Sales Cloud OData APIs.

For more information, see [Configure the OAuth Client for OData Access](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/2c9c02d7d19748eea0d2482093f04278.html).



### Prerequisites

-   You know the name of the identity provider created in [Configure OAuth Identity Provider in SAP Sales Cloud](50-Development/sap-sales-cloud-a22152f.md#loioa22152f0f53a48bdbb4385cd438e0324__OAuth_SalesCloud).



### Handover Information to the SAP BTP Administrator

-   Client ID
-   Client secret
-   Scope



<a name="copy5c50b2bfb97749cca202943756de92bc__section_pyk_yc5_vxb"/>

## Create Destinations

As the SAP BTP administrator, you must create and configure an HTTP destination that either supports principal propagation or is based on a technical user.



### Destination for Identity Propagation

**Prerequisites**

The SAP Sales Cloud administrator has configured the communication between Graph and SAP Sales Cloud. You know the following:

-   Client ID
-   Client secret
-   Scope

**Procedure**

As the SAP BTP administrator, you must create and configure an HTTP destination that supports principal propagation. For more information, see [Create and Configure the HTTP Destination](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/21e50d89d0904038b98e604c8ed85de3.html?version=Cloud).



### Destination with a Technical User

**Procedure**

Create a *BasicAuthentication* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit*Connectivity* \> *Destinations* and choose *New Destination*. Enter the following:


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
    
    `BasicAuthentication` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    The name of the communication user in the SAP Sales Cloud tenant.
    
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


