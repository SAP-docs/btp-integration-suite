<!-- loio542fb116e71641e3a0d8ddb130447376 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Trading Partner Profile

A trading partner is a company, organization, or a subsidiary that conducts e-business \(B2B\) with other companies, organizations or subsidiaries.

A trading partner profile provides information about a company, organization, or subsidiary, which is relevant for setting up a trading partner agreement. It includes the business context, contact, systems involved, communication parameters, certificates, active B2B scenarios, message implementation guidelines, functional or application acknowledgements, as well as the identifications and further parameters necessary to uniquely identify the specific trading partner in an receiving interchange as well as setting the appropriate information in the envelopes of a sending interchange.

Follow the procedure below to create a trading partner profile



<a name="loio542fb116e71641e3a0d8ddb130447376__section_hbc_dfs_kqb"/>

## Procedure

1.  Log on to your Integration Suite .
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to the *Trading Partners* tab and choose *Create* to add a new trading partner.
4.  Under the *Overview* tab, maintain the following fields under the *Details* section

    **Details**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Company Name


    
    </td>
    <td valign="top">
    
    Provide a valid name of your company. This field is mandatory.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Company Short Name


    
    </td>
    <td valign="top">
    
    Enter a short name of your company. This field is mandatory.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL


    
    </td>
    <td valign="top">
    
    The web link to access your company


    
    </td>
    </tr>
    </table>
    
5.  You can also provide the address of your company under the *Address* section.
6.  Choose *Save* .

    > ### Note:  
    > The *Logo* field is disabled initially. You can upload an image after saving the above mentioned entries. To do so, choose *Edit* and select *Browse* to search and upload your company logo.

7.  Navigate to the *Contact* tab.
8.  Choose Create and provide the following information

    **Contact Details**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    First Name


    
    </td>
    <td valign="top">
    
    A valid first name of the contact


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Second Name


    
    </td>
    <td valign="top">
    
    Provide the second/last name of the contact


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role


    
    </td>
    <td valign="top">
    
    The role of the contact in the company


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EMail


    
    </td>
    <td valign="top">
    
    A valid email ID of the contact


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Phone


    
    </td>
    <td valign="top">
    
    A valid phone number of the contact


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address


    
    </td>
    <td valign="top">
    
    The address of the contact person


    
    </td>
    </tr>
    </table>
    
9.  Choose *Save*. You can also modify or delete the contact details using the edit :pencil2: and delete :wastebasket: buttons respectively.
10. Navigate to the *Identifier* tab and choose *Create*.
11. In the resulting dialog box, enter the following details

    **Identifier**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Identification


    
    </td>
    <td valign="top">
    
    Provide a valid ID for the identifier


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias


    
    </td>
    <td valign="top">
    
    Enter an alias to the identifier

    > ### Note:  
    > An Alias is a user provided, tenant independent identifier for artifacts, that can be used to maintain referential integrity in cross tenant use cases like transport. To know more, see [Understanding the Basic Concepts](understanding-the-basic-concepts-74c068d.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System


    
    </td>
    <td valign="top">
    
    Choose a type system from the drop-down list

    > ### Note:  
    > For *GS1 XML* type system, you must maintain the contact details in the *Contacts* tab.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme


    
    </td>
    <td valign="top">
    
    Choose a scheme from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Agency


    
    </td>
    <td valign="top">
    
    Provide the agency name and code in their respective fields


    
    </td>
    </tr>
    </table>
    
12. Choose *Save* and navigate to *Business Context*.
13. Choose *Edit* and enter the following information

    **Business Context**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Process Role


    
    </td>
    <td valign="top">
    
    Choose the process role of your business from the drop-down list. You can assign more than one process role.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Industry Classification


    
    </td>
    <td valign="top">
    
    Choose the industry that your business belongs to using the drop-down list. You can add multiple entries.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Product Classification


    
    </td>
    <td valign="top">
    
    Choose the category to which your product belongs to. You can add multiple entries.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Country/Region


    
    </td>
    <td valign="top">
    
    Choose the country details from the drop-down list


    
    </td>
    </tr>
    </table>
    
14. Choose *Save* and navigate to the *System* tab.
15. Choose *Create* to add the following system details.

    **System**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name


    
    </td>
    <td valign="top">
    
    Enter a valid name for the system.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias


    
    </td>
    <td valign="top">
    
    Enter an alias for the system.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type


    
    </td>
    <td valign="top">
    
    Select the type of the system from the drop-down list.

    If you want to modify the system type details, choose the edit icon :pencil2:

    If your system type is not available in the list, choose add :heavy_plus_sign: and enter the details of the new system and choose *Apply*. The newly created system will be selected now in the *Type* field.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Purpose


    
    </td>
    <td valign="top">
    
    Select the purpose of the type system from the drop-down list. You can choose *Dev*, *Test* or *Prod*. The value that you set here will be picked up during the agreement activation to denote in the payload the purpose of the transaction.

    To know more, see [Payload Indicator in Integration Flow Message Processing](payload-indicator-in-integration-flow-message-processing-7f322c0.md)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Link


    
    </td>
    <td valign="top">
    
    Provide a link to the system


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description


    
    </td>
    <td valign="top">
    
    Provide a description for the system


    
    </td>
    </tr>
    </table>
    
16. Choose *Save*. The system gets created successfully.
17. You also need to configure the type system and communication channel details for the newly created company profile and hence its *Status* is set to *Incomplete*.

    > ### Note:  
    > To know more about type systems, see [Terminology for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/9c221b48799a4ce59367b0e3367f5a8f.html)

18. To do so, select the newly created system and under the *Type System* tab, choose *Create*.
19. In the *Create Type System* dialog, select the *Name* and *Version* of the type system from the drop-down list.
20. Choose *Save*. The type system is added successfully. Choose *Save* to update the system.
21. Navigate to the *Communication* tab and choose *Create*.
22. Maintain the following fields

    **Communication Details**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name


    
    </td>
    <td valign="top">
    
    Enter a valid name for your communication


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias


    
    </td>
    <td valign="top">
    
    Enter an alias for the communication


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description


    
    </td>
    <td valign="top">
    
    Provide a description


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Direction


    
    </td>
    <td valign="top">
    
    Choose whether the communication channel is a *Sender* or *Receiver*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter


    
    </td>
    <td valign="top">
    
    Select an adapter from the drop-down list.

    > ### Note:  
    > The supported adapters for *Sender* communication are:
    > 
    > -   AS2
    > 
    > -   AS2 MDN
    > -   IDOC
    > -   SOAP 1.x
    > 
    > The supported adapters for *Receiver* communication are:
    > 
    > -   AS2
    > 
    > -   IDOC
    > -   SAP RM
    > -   SOAP\_1.x


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Account

    > ### Note:  
    > This field appears only when you choose *AS2* as the Sender adapter.


    
    </td>
    <td valign="top">
    
    Enter the user account that you have configured in Cloud Integration tenant for authorisation.

    To know more, see [Partner Authorization](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/c0c9950003674d198e9e7ceda098053d.html).


    
    </td>
    </tr>
    </table>
    
23. The *Connection* tab appears when you choose *SOAP\_1.x* or *SAP RM* or *IDOC* as the receiver adapter. Maintain the following fields:

    **Connection**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Address


    
    </td>
    <td valign="top">
    
    Endpoint address at which Cloud Integration posts the outgoing message.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type


    
    </td>
    <td valign="top">
    
    Select the proxy type from the drop-down list.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID

    > ### Note:  
    > This field appears only when you set the value *On-Premise* for the *Proxy Type*


    
    </td>
    <td valign="top">
    
    Enter the location ID that you specified for the destination configuration.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication


    
    </td>
    <td valign="top">
    
    Set the authentication mode using the drop-down list.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name

    > ### Note:  
    > This field appears when you choose *Basic* authentication.


    
    </td>
    <td valign="top">
    
    Enter the credential name for basic authentication.


    
    </td>
    </tr>
    </table>
    
24. The following tabs appear when you choose AS2 receiver adapter. Maintain the following fields:

    **Connection**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Receipient URL


    
    </td>
    <td valign="top">
    
    Enter the URL of the receiver system


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type


    
    </td>
    <td valign="top">
    
    Select the type of proxy you want to use for connecting to receiver system.

    -   Internet

    -   On-Premise
    -   Dynamic


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Type


    
    </td>
    <td valign="top">
    
    Select one of the following authentication methods:

    -   None

    -   Basic Authentication
    -   Client Certificate
    -   Dynamic


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name

    Only if you choose *Basic Authentication*


    
    </td>
    <td valign="top">
    
    Provide the credentials for basic authentication


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias

    Only if you choose *Client Certificate* for aunthentication


    
    </td>
    <td valign="top">
    
    Specify the private key alias for the AS2 message authentication.


    
    </td>
    </tr>
    </table>
    
    Select the *Processing* tab and maintain the following fields:

    **Processing**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    File Name


    
    </td>
    <td valign="top">
    
    Specify the AS2 file name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Append Timestamp


    
    </td>
    <td valign="top">
    
    Appends a timestamp at the end of the file name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message ID Left Part


    
    </td>
    <td valign="top">
    
    Specify the left side of the AS2 message ID. Regular expression or '.\*' is allowed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message ID Right Part


    
    </td>
    <td valign="top">
    
    Specify the right side of the AS2 message ID. Regular expression or '.\*' is allowed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Own AS2 ID


    
    </td>
    <td valign="top">
    
    Specify your own AS2 ID. Regular expression or '.\*' is allowed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partner AS2 ID


    
    </td>
    <td valign="top">
    
    Specify the partner's AS2 ID.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Subject


    
    </td>
    <td valign="top">
    
    Specify an AS2 message subject.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Own E-mail address


    
    </td>
    <td valign="top">
    
    Specify your own e-mail address.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Content-Type


    
    </td>
    <td valign="top">
    
    Enter the content type of the outgoing message.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Content Transfer Encoding


    
    </td>
    <td valign="top">
    
    Select the AS2 message encoding type from the drop-down list.


    
    </td>
    </tr>
    </table>
    
    Select the *Security* tab and maintain the following fields:

    **Security**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Compress Message


    
    </td>
    <td valign="top">
    
    Select this checkbox to ensure that the outgoing AS2 message is compressed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Sign Message


    
    </td>
    <td valign="top">
    
    Select this checkbox to ensure that the outgoing AS2 message is signed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Encrypt Message


    
    </td>
    <td valign="top">
    
    Select this checkbox to ensure that the message is encrypted.


    
    </td>
    </tr>
    </table>
    
    Select the *MDN* tab and maintain the following fields:

    **MDN**


    <table>
    <tr>
    <th valign="top">

    Field


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Type


    
    </td>
    <td valign="top">
    
    Choose one of the following for the MDN request:

    -   Asynchronous

    -   None
    -   Synchronous


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Request Signing

    \(only if you select the *Synchronous* or *Asynchronous* MDN type\)


    
    </td>
    <td valign="top">
    
    Enable this option to request the partner to sign AS2 MDN.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Request MIC

    \(only if you select the *Synchronous* or *Asynchronous* MDN type\)


    
    </td>
    <td valign="top">
    
    Enable this option if you want to request an integrity check.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Failure on Negative MDN

    \(only if you select the *Synchronous* MDN type\)


    
    </td>
    <td valign="top">
    
    Enable this option to set message status to *Failed* on negative MDN.


    
    </td>
    </tr>
    </table>
    
25. If you select AS2 as the *Sender* adapter, two new fields appear:

    -   *Security Configuration Mode*: Set your configuration mode to *Profile* or *Channel* from the drop-down list.

        > ### Note:  
        > It is highly recommended to use *Profile* mode as this mode supports reuse of configurations. *Channel* mode is only used for backward compatibility.

    -   *User Account*: Enter the user account in this field. This field appears for *Channel* mode.
    -   *AS2 Partner ID*: Select a partner ID from the drop-down list. This field appears for *Profile* mode.

    If you chose *Channel* as the configuration mode, the following tabs appear.

    **MDN**


    <table>
    <tr>
    <th valign="top">

    Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias for Signature


    
    </td>
    <td valign="top">
    
    This field should be maintained under the *Security* tab to sign the MDN on partner's request.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Signature Encoding


    
    </td>
    <td valign="top">
    
    Select the MDN signature encoding type from the drop-down list.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type


    
    </td>
    <td valign="top">
    
    Select the proxy type using which the request is sent to the receiver.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID

    \(Only if you chose *On-Premise* as the *Proxy Type*.\)


    
    </td>
    <td valign="top">
    
    Enter the location ID to connect to the cloud connector associated with your account.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication


    
    </td>
    <td valign="top">
    
    Select the authentication type for your MDN.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name

    \(Only if you chose *Basic Authentication*\)


    
    </td>
    <td valign="top">
    
    Select the deployed user credential alias from the drop-down list.


    
    </td>
    </tr>
    </table>
    
    **Security**


    <table>
    <tr>
    <th valign="top">

    Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Decrypt Message


    
    </td>
    <td valign="top">
    
    Select this checkbox to ensure that the message is decrypted.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias

    \(only if you select *Decrypt Message*\).


    
    </td>
    <td valign="top">
    
    Specify the private key alias to decrypt the AS2 message.

    > ### Note:  
    > You need to first maintain the Private Key Alias in the Keystore of the Cloud Integration tenant.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Verify Signature


    
    </td>
    <td valign="top">
    
    Ensure that the signature is verified by selecting one of the following options:

    -   *Not Required*

    -   *Trusted Certificate*: Used to verify the Signature.

    -   *Trusted Root Certificate*: The trust chain begins with the use of the public alias as an intermediate certificate to verify the inbound certificate. After successful verification the inbound certificate is used to verify the Signature.

        > ### Note:  
        > If *Trusted Root Certificate* is selected mention the public key alias immediate root certificate of the incoming message.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Public Key Alias \(Only if you have selected *Trusted Certificate* or *Trusted Root Certificate*\)


    
    </td>
    <td valign="top">
    
    Specify the public key alias\(in case of *Trusted Certificate*\) or public key aliases\(in case of *Trusted Root Certificate*\) to verify the signature of the AS2 message.

    > ### Note:  
    > You need to first maintain the certicates under the *Certificates* tab of the trading partner profile.


    
    </td>
    </tr>
    </table>
    
    If you chose *Profile* as the configuration mode, the following tabs appear:

    *AS2 Partner ID* field:

    Select a partner ID from the drop-down list.

    > ### Note:  
    > You need to maintain the values of the fields in the *Security* tab of your trading partner profile.

    *AS2 Partner ID*

    This tab values get auto-filled based on the value you choose for the *AS2 Partner ID* field above.

    **MDN**


    <table>
    <tr>
    <th valign="top">

    Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias for Signature


    
    </td>
    <td valign="top">
    
    This field should be maintained under the *Security* tab of your trading partner profile.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Signature Encoding


    
    </td>
    <td valign="top">
    
    Select the MDN signature encoding type from the drop-down list.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type


    
    </td>
    <td valign="top">
    
    Select the proxy type using which the request is sent to the receiver.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID

    \(Only if you chose *On-Premise* as the *Proxy Type*.\)


    
    </td>
    <td valign="top">
    
    Enter the location ID to connect to the cloud connector associated with your account.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication


    
    </td>
    <td valign="top">
    
    Select the authentication type for your MDN.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name

    \(Only if you chose *Basic Authentication*\)


    
    </td>
    <td valign="top">
    
    Select the deployed user credential alias from the drop-down list.


    
    </td>
    </tr>
    </table>
    
26. Choose *Save*.

    > ### Note:  
    > You need to maintain both *Sender* and *Receiver* communication channel details to complete the system set-up.
    > 
    > After maintaining the necessary details, the *Status* of the System is set to *Completed*.

27. Navigate to the *Certificate* tab and choose *Create*.
28. Maintain the following details

    **Certificate**


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Alias


    
    </td>
    <td valign="top">
    
    Provide an alias name for the certificate


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    File


    
    </td>
    <td valign="top">
    
    Browse and upload the certificate


    
    </td>
    </tr>
    </table>
    
29. Choose Add. The certificate gets added successfully. You can perform other actions on this certificate using the actions <span class="SAP-icons"></span> button

The application also allows you to maintain Dynamic Parameters under the trading partner profile. These parameters can be helpful when

-   You use custom integration flow.

-   You need to provide parameters for the main mapping step in a integration flow.
-   When you use GS1 XML type system in your agreement and that requires dynamic parameters. These are the following parameters that you can define for GS1 XML type system:
    -   SAP\_EDI\_REC\_Sender\_Partner\_Type

    -   SAP\_EDI\_REC\_Receiver\_Partner\_Type
    -   SAP\_EDI\_REC\_Header\_Version
    -   SAP\_EDI\_REC\_Multiple\_Type
    -   SAP\_EDI\_REC\_Message\_Business\_Scope\_Type
    -   SAP\_EDI\_REC\_Message\_Busines\_Scope\_Instance
    -   SAP\_EDI\_REC\_Message\_Business\_Scope


To do so, you need to upload the parameters in a *csv* file format.

1.  Navigate to the *Parameters* tab of the trading partner profile.

2.  In the *Import File* dialog, choose *Browse* to select and upload a csv file.
3.  Choose a type of the csv file under the *Type* field.
4.  Select the field seperator of the csv file from the drop-down list of the field *Field Seperator in CSV*.
5.  Choose *Next*. The next screen displays a preview of the parameters in the csv file.
6.  Choose *Import*. The parameters are now successfully added to the trading partner profile.

When you use AS2 adapters in your agreements, you need to maintain few decryption configurations. To do so,

1.  Navigate to the *Security* tab and choose *Create*.

2.  Maintain the following fields:
    1.  *User Account*: Enter the user account name.

    2.  *Alias*: Maintain an alias for the configuration.
    3.  *Private Key Alias*: Enter a Private Key Alias for the configuration.

3.  Choose *Save* after maintaining all the fields. These configurations should be activated in order to be used in an Agreement. Select the toggle button below the *Activation Status* header to activate your configuration.

    Once activated, the AS2 Partner ID details are pushed into the Partner Directory.

    > ### Note:  
    > If you maintain the following ID entries and use them in an agreement, then on activating the agreement, the IDs could interefere and overwrite the existing AS2 partner ID based scenarios that are configured outside the Trading Partner Management solution. To avoid this, it is suggested to use a different partner ID.

    **AS2 Partner ID Data**


    <table>
    <tr>
    <th valign="top">

    Partner Directory ID


    
    </th>
    <th valign="top">

    Adapter


    
    </th>
    <th valign="top">

    Type


    
    </th>
    <th valign="top">

    Defined by the system


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Authentication


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    Authentication mode for Asynchronous MDN


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Mdn\_Verify\_Mic


    
    </td>
    <td valign="top">
    
    AS2 MDN Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    If verify MIC for MDN is required


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Mdn\_Verify\_Signature


    
    </td>
    <td valign="top">
    
    AS2 MDN Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    If verify signature for MDN is required


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Proxy\_Type


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    Proxy Type for Asynchronous MDN


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Signature\_Encoding


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    Signature encoding for MDN


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Verify\_Signature


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    Yes


    
    </td>
    <td valign="top">
    
    If signature verification is required for EDI. This value overwrite the PD entries with ID AS2\_inbound\_verify\_signature


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_MDN\_CredentialName


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    No


    
    </td>
    <td valign="top">
    
    Credential Name for Basic Authentication in Asynchronous MDN


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_MDN\_LocationId


    
    </td>
    <td valign="top">
    
    AS2 Sender


    
    </td>
    <td valign="top">
    
    String


    
    </td>
    <td valign="top">
    
    No


    
    </td>
    <td valign="top">
    
    Location ID for On-Premise in Asynchronous MDN


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Public\_Key


    
    </td>
    <td valign="top">
    
    AS2 Sender/AS2 MDN Sender


    
    </td>
    <td valign="top">
    
    Binary


    
    </td>
    <td valign="top">
    
    No


    
    </td>
    <td valign="top">
    
    Public key for signature verification for EDI / MDN


    
    </td>
    </tr>
    </table>
    

You have now successfully created a trading partner profile and you can view the partner details under the *Trading Partners* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date



**Related Information**  


[Creating an Agreement Template](creating-an-agreement-template-9692cb1.md "An agreement template is a template of a semantical choreography definition consisting of one or more business transactions. The configurations at the template level serve as defaults that can then be reused and overridden when creating the trading partner agreement.")

