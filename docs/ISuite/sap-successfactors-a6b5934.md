<!-- copya6b5934e35dd4876a1102be9d2b189ae -->

# SAP SuccessFactors

As an SAP SuccessFactors and SAP BTP administrator, you need to set up the connectivity to Graph and create destinations.:

1.  Download the certificate from the *Destination* service of your SAP BTP account.
2.  Create an OAuth client in SAP SuccessFactors.
3.  Create the *Destination* on your SAP BTP Destination service.



<a name="copya6b5934e35dd4876a1102be9d2b189ae__section_nwq_k1l_xrb"/>

## Download the Trust Certificate from the Destination Service

As the SAP BTP subaccount administrator, download the trust certificate from your account’s destination service.



### Procedure

1.  In the SAP BTP cockpit, go to your subaccount in the SAP BTP, Cloud Foundry environment.
2.  Choose *Connectivity* \> *Destinations*.
3.  Choose *Download Trust* to get the certificate for this subaccount and save it to your local file system.



<a name="copya6b5934e35dd4876a1102be9d2b189ae__section_lrs_r1l_xrb"/>

## Create an OAuth Client on SAP SuccessFactors

As the SAP SuccessFactors administrator, you need to create an OAuth client that will be used to configure the trust between SAP SuccessFactors and Graph.



### Procedure

1.  In the SAP SuccessFactors system, go to the *Admin Center* and search for *OAuth*. Choose *Manage OAuth2 Client Applications* from the search results.
2.  Choose *Register Client Application*.
3.  In the *Application Name*, choose a descriptive name for the client of your choice.
4.  In the *Application URL* field, enter the URL of yourGraph tenant.
5.  In the *X.509 Certificate* field, open the certificate you downloaded before from the Destination service using any text editor, then copy the content between `-----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----`, and paste it into the field.
6.  Choose *Register* to save the OAuth client.



<a name="copya6b5934e35dd4876a1102be9d2b189ae__section_zbn_qd5_vxb"/>

## Create Destinations

As the SAP BTP administrator, you need to create an HTTP destination to be able to make calls to the SAP SuccessFactors HCM Suite OData APIs using SAML 2.0 Bearer Assertion authentication.



### Procedure

1.  In the SAP BTP cockpit, go to your subaccount in the SAP BTP, Cloud Foundry environment.
2.  Choose *Connectivity* \> *Destinations*.
3.  Choose *New Destination* and fill in the following parameters:


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
    
    Enter the URL of the SAP SuccessFactors OData API that you want to consume. For a list of the API Endpoint URLs for the SAP SuccessFactors environments, see [About HXM Suite OData APIs](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/28bc3c8e3f214ab487ec51b1b8709adc/03e1fc3791684367a6a76a614a2916de.html)
    
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
    
    `OAuth2SAMLBearerAssertion`
    
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
    
    `www.successfactors.com` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    AuthnContextClassRef
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    Enter the API Key of the OAuth client that you created in SAP SuccessFactors.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Enter the API Endpoint URL for the SAP SuccessFactors instance followed by`/oauth/token`. For example,`https://apisalesdemo2.successfactors.eu/oauth/token`. For a list of the API Endpoint URLs for the SAP SuccessFactors environments, see [About HXM Suite OData APIs](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/).
    
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
    </table>
    
4.  Configure the required additional properties. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following parameters:


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
    
    apiKey
    
    </td>
    <td valign="top">
    
    Enter the API Key of the OAuth client that you created in SAP SuccessFactors.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    companyId
    
    </td>
    <td valign="top">
    
    The ID of your SAP SuccessFactors company.
    
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
    
    userIdSource
    
    </td>
    <td valign="top">
    
    `email`
    
    </td>
    </tr>
    </table>
    
5.  Select the *Use default JDK truststore* checkbox.

6.  Click *Save*.


