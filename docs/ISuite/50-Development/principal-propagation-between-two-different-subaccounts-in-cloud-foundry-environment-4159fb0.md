<!-- loio4159fb0700be40c28327e43a656ef2c3 -->

# Principal Propagation Between Two Different Subaccounts in Cloud Foundry Environment

Propagate the identity of a user between two Cloud Foundry applications that are located in different subaccounts or regions.



<a name="loio4159fb0700be40c28327e43a656ef2c3__prereq"/>

## Prerequisites

-   You have two applications \(application 1 and application 2\) deployed in Cloud Foundry environment in different subaccounts in the same region or in different regions.

    Application 1 resides in subaccount 1 and application 2 resides in subaccount 2.

-   You have an instance of the Destination service bound to application 1.
-   You have a user JWT \(JSON Web Token\) in application 1 where the call to application 2 is performed.



<a name="loio4159fb0700be40c28327e43a656ef2c3__procedure"/>

## Procedure



### Assemble IdP Metadata for Subaccount 1 

1.  From *Subaccount 1* \> *Destinations* \> *Download Trust*, download the X.509 certificate of subaccount 1. The content of the file is shown as:

    ```
    -----BEGIN CERTIFICATE-----<content>-----END CERTIFICATE-----
    ```

    We refer to the value of <content\> as `${S1_CERTIFICATE}`.

2.  In the cockpit, navigate to the overview page of subaccount 1. Here you can see the landscape domain, subaccount ID, and subdomain. Below we refer to the landscape domain as `${S1_LANDSCAPE_DOMAIN}`, to the subaccount ID as `${S1_SUBACCOUNT_ID}` and to the subdomain as `${S1_SUBDOMAIN}`.
3.  In your browser, call `https://${S1_SUBDOMAIN}.authentication.${S1_LANDSCAPE_DOMAIN}/saml/idp/metadata` and download the XML file. Within the XML file you can find the following structure:

    > ### Sample Code:  
    > ```
    > <?xml version="1.0" encoding="UTF-8"?>
    > <md:EntityDescriptor xmlns:md="urn:oasis:names:tc:SAML:2.0:metadata" ID="<id>" entityID="<alias>">
    > ...
    > </md:EntityDescriptor>
    > ```

    We refer to the value of <alias\> as `${S1_ALIAS}`.

4.  Assemble the new IdP metadata for subaccount 1 by replacing the `${...}` placeholders in the following template with the values determined in the previous steps:

    > ### Sample Code:  
    > ```
    > <ns3:EntityDescriptor
    >     ID="cfapps.${S1_LANDSCAPE_HOST}/${S1_SUBACCOUNT_ID}"
    >     entityID="cfapps.${S1_LANDSCAPE_HOST}/${S1_SUBACCOUNT_ID}"
    >     xmlns="http://www.w3.org/2000/09/xmldsig#"
    >     xmlns:ns2="http://www.w3.org/2001/04/xmlenc#"
    >     xmlns:ns4="urn:oasis:names:tc:SAML:2.0:assertion"
    >     xmlns:ns3="urn:oasis:names:tc:SAML:2.0:metadata">
    >     <ns3:SPSSODescriptor AuthnRequestsSigned="true"
    >         protocolSupportEnumeration="urn:oasis:names:tc:SAML:2.0:protocol">
    >         <ns3:KeyDescriptor use="signing">
    >             <KeyInfo>
    >                 <KeyName>${S1_ALIAS}</KeyName>
    >                 <X509Data>
    >                     <X509Certificate>
    >                         ${S1_CERTIFICATE}
    >                     </X509Certificate>
    >                 </X509Data>
    >             </KeyInfo>
    >         </ns3:KeyDescriptor>
    >     </ns3:SPSSODescriptor>
    >     <ns3:IDPSSODescriptor
    >         WantAuthnRequestsSigned="true"
    >         protocolSupportEnumeration="urn:oasis:names:tc:SAML:2.0:protocol">
    >         <ns3:KeyDescriptor use="signing">
    >             <KeyInfo>
    >                 <KeyName>${S1_ALIAS}</KeyName>
    >                 <X509Data>
    >                     <X509Certificate>
    >                         ${S1_CERTIFICATE}
    >                     </X509Certificate>
    >                 </X509Data>
    >             </KeyInfo>
    >         </ns3:KeyDescriptor>
    >     </ns3:IDPSSODescriptor>
    > </ns3:EntityDescriptor>
    > ```




### Establish Trust between Subaccount 1 and Subaccount 2

1.  In the cockpit, navigate to the overview page for subaccount 2.
2.  From the left panel, select *Security* \> *Trust Configuration*. Choose *New Trust Configuration*.
3.  Paste the assembled IdP metadata for subaccount 1 in the *<Metadata\>* text box and uncheck *Available for User Logon*.
4.  Choose *Parse*.
5.  Enter a *<Name\>* for the trust configuration and choose *Save*.

> ### Note:  
> Additionally, you must add users to this new trust configuration and assign appropriate scopes to them.



### Create an OAuthSAMLBearerAssertion Destination for Application 1

1.  In the cockpit, navigate to the overview page for subaccount 2.
2.  Here you can see the landscape domain, subaccount ID and subdomain of subaccount 2. We refer to the landscape domain as `${S2_LANDSCAPE_DOMAIN}`, to the subaccount ID as `${S2_SUBACCOUNT_ID}` and to the subdomain as `${S2_SUBDOMAIN}`.
3.  In your browser, call `https://${S2_SUBDOMAIN}.authentication.${S2_LANDSCAPE_DOMAIN}/saml/idp/metadata` and download the XML file. Within the XML file, you can find the following structure.

    > ### Sample Code:  
    > ```
    > <?xml version="1.0" encoding="UTF-8"?>
    > <md:EntityDescriptor xmlns:md="urn:oasis:names:tc:SAML:2.0:metadata" ID="<id>" entityID="<alias>">
    > ...
    > </md:EntityDescriptor>
    > <md:AssertionConsumerService 
    > Binding="urn:oasis:names:tc:SAML:2.0:bindings:URI" 
    > Location="<token>" index="1"/></md:SPSSODescriptor>
    > </md:EntityDescriptor> Token= ${S2_Token_URL}
    > ```

    We refer to the value of <alias\> as `${S2_ALIAS}`.

4.  In cockpit, navigate to subaccount 1.
5.  From the left panel, select *Connectivity* \> *Destinations*.
6.  Choose *New Destination* and configure the values as described below. Replace the `${…}` placeholders with the values you determined in the previous steps and sections.


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `Name`
    
    </td>
    <td valign="top">
    
    Choose any name for your destination. You use this name to request the destination from the Destination service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Type`
    
    </td>
    <td valign="top">
    
    `HTTP`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `URL`
    
    </td>
    <td valign="top">
    
    The URL of application 2, identifying the resource you want to consume.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Proxy Type`
    
    </td>
    <td valign="top">
    
    `Internet`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Authentication`
    
    </td>
    <td valign="top">
    
    `OAuth2SAMLBearerAssertion`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Audience`
    
    </td>
    <td valign="top">
    
    `entityId`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Client Key`
    
    </td>
    <td valign="top">
    
    The *clientid* of the XSUAA instance in subaccount 2. Can be acquired via a binding or service key.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Token Service URL`
    
    </td>
    <td valign="top">
    
    The URL of the XSUAA instance in subaccount 2. Can be acquired from <token\>.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Token Service URL Type`
    
    </td>
    <td valign="top">
    
    `Dedicated`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Token Service User`
    
    </td>
    <td valign="top">
    
    The *clientid* of the XSUAA instance in subaccount 2. Can be acquired via a binding or service key.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Token Service Password`
    
    </td>
    <td valign="top">
    
    The *clientsecret* of the XSUAA instance in subaccount 2. Can be acquired via a binding or service key.
    
    </td>
    </tr>
    </table>
    
    **Additional Properties**


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
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
    
    `authnContextClassRef`
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`
    
    </td>
    </tr>
    </table>
    
7.  Choose *Save*.



### Consume the Destination and Execute the Scenario 

To perform the scenario and execute the request from application 1, targeting application 2, proceed as follows:

1.  Decide on where the user identity will be located when calling the Destination service. For details, see [User Propagation via SAML 2.0 Bearer Assertion Flow](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/3cb7b81115c44cf594e0e3631291af94.html). This will determine how exactly you will perform step 2.
2.  Execute a "find destination" request from application 1 to the Destination service. For details, see [Consuming the Destination Service](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/7e306250e08340f89d6c103e28840f30.html) and the [REST API documentation](https://api.sap.com/api/SAP_CP_CF_Connectivity_Destination/resource).
3.  From the Destination service response, extract the access token and URL, and construct your request to application 2. See ["Find Destination" Response Structure](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/83a3f3b9cd314618aba651044ed5b9df.html) for details on the structure of the response from the Destination service.

