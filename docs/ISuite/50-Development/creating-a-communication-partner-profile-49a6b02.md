<!-- loio49a6b02fa47247efa1707f4248fe22a5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Communication Partner Profile

Create a Communication Partner profile.



## Context

A communication partner profile is similar to trading partner profile. Using a communication partner profile, you can create AS2 specific configurations and use them across other entities. Most of the AS2 specific agreements and templates have different trading partners, identifiers and type systems, but they almost have the same AS2 configurations. Instead of defining them individually for each trading partner profile, you can now define them once in your communication partner and reuse them indefinitely. To know more about creating such partner, follow the procedure below.



## Procedure

1.  Login to your application and navigate to *Design* \> *B2B Scenarios* from the left pane.

2.  In the resulting screen, navigate to *Partner Profiles* tab.

3.  Choose *Create* and select *Communication Partner* from the drop-down list.

4.  Under the *Overview* tab, maintain the following fields under the *Details* section:


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
    
    **Company Name**
    
    </td>
    <td valign="top">
    
    Provide a valid name of your company. This field is mandatory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Company Short Name**
    
    </td>
    <td valign="top">
    
    Enter a short name of your company. This field is mandatory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **URL**
    
    </td>
    <td valign="top">
    
    The web link to access your company
    
    </td>
    </tr>
    </table>
    
5.  You can also provide the address of your company under the *Address* section.

6.  Choose *Save* to save your changes.

7.  Navigate to the *Systems* tab and choose *Create System*.

8.  In the*Create System* dialog, maintain the following fields:


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
    
    **Name**
    
    </td>
    <td valign="top">
    
    Enter a valid name for the system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Alias**
    
    </td>
    <td valign="top">
    
    Enter an alias for the system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type**
    
    </td>
    <td valign="top">
    
    Select the type of the system from the drop-down list.

    If you want to modify the system type details, choose the edit icon :pencil2:

    If your system type is not available in the list, choose add :heavy_plus_sign: and enter the details of the new system and choose *Apply*. The newly created system will be selected now in the *Type* field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Purpose**
    
    </td>
    <td valign="top">
    
    Select the purpose of the type system from the drop-down list. You can choose *Dev*, *Test* or *Prod*. The value that you set here will be picked up during the agreement activation to denote in the payload the purpose of the transaction.

    To know more, see [Payload Indicator in Integration Flow Message Processing](payload-indicator-in-integration-flow-message-processing-7f322c0.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Link**
    
    </td>
    <td valign="top">
    
    Provide a link to the system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**
    
    </td>
    <td valign="top">
    
    Provide a description for the system.
    
    </td>
    </tr>
    </table>
    
9.  Choose *Save*. The new system gets created.

10. The *Status* of this newly created system is set to *Incomplete* as you need to configure the communication channel details for the system. Open the system and choose *Create Communication*.

11. In the *Add Communication* dialog, maintain the following fields:


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
    
    **Name**
    
    </td>
    <td valign="top">
    
    Enter a valid name for your communication
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Alias**
    
    </td>
    <td valign="top">
    
    Enter an alias name for your communication
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**
    
    </td>
    <td valign="top">
    
    Provide a meaningful description
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Direction**
    
    </td>
    <td valign="top">
    
    Choose whether the communication channel is a *Sender* or *Receiver*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Adapter**
    
    </td>
    <td valign="top">
    
    Select an adapter from the drop-down list.

    > ### Note:  
    > Only AS2 adapter is supported adapters for *Sender* and *Receiver* communication.


    
    </td>
    </tr>
    </table>
    
12. If you chose *AS2* for the *Sender*, the following fields appear:

    1.  *Security Configuration Mode*: Set your configuration mode to *Profile* or *Channel* from the drop-down list.

        > ### Note:  
        > It is highly recommended to use *Profile* mode as this mode supports reuse of configurations. *Channel* mode is only used for backward compatibility.

    2.  *User Account*: Enter the user account in this field. This field appears for *Channel* mode.

    3.  *AS2 Partner ID*: Select a partner ID from the drop-down list. This field appears for *Profile* mode.


13. If you chose *Channel* as the configuration mode, you need to maintain the following tabs that appear below the fields:

    **MDN Tab**


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
    
    **Security Tab**


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
    
14. If you chose *Profile* as the configuration mode, maintain the following tabs:

    > ### Note:  
    > The *AS2 Partner ID* tab gets auto-filled based on the values provided in th fields above.

    **MDN Tab**


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
    
15. If you chose *AS2* adapter for your *Receiver* communication, maintain the following tabs:

    **Connection Tab**


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
    
    Enter the URL of the AS2 receiver system
    
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


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID \(only if you chose *On-Premise* for the *Proxy Type*\)
    
    </td>
    <td valign="top">
    
    Enter the location ID that you defined for this instance in the destination configuration.
    
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
    </table>
    
    **Processing Tab**


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
    
    Include Millisecond \(appears only if you select the checkbox for *Append Timestamp*\)
    
    </td>
    <td valign="top">
    
    Select this checkbox if you want milliseconds to be included the AS2 timestamp \(yyyyMMddHHmmssSSS\).
    
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
    
    **Security Tab**


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
    
    Algorithm \(appears only if you select the checkbox for *Sign Message*\)
    
    </td>
    <td valign="top">
    
    Select an AS2 message signing algorithm from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias \(appears only if you select the checkbox for *Sign Message*\)
    
    </td>
    <td valign="top">
    
    Specify the private key alias to sign the AS2 message.
    
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
    <tr>
    <td valign="top">
    
    Algorithm \(appears only if you select the checkbox for *Encyrpt Message*\)
    
    </td>
    <td valign="top">
    
    Select an AS2 encryption algorithm from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Public Key Alias \(appears only if you select the checkbox for *Encrypt Message*\)
    
    </td>
    <td valign="top">
    
    Specify the public key alias to encrypt the AS2 message.
    
    </td>
    </tr>
    </table>
    
    **MDN Tab**


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
    
16. Choose *Save*.

17. Navigate to the *Certificates* tab and choose *Create Certificate*.

18. In the *Add Certificate* dialog, enter an alias for the certificate in the *Alias* field.

19. Choose *Browse* to browse and upload a certificate to the *File* field.

20. Choose *Add*. The certificate is added successfully.

21. Navigate to the *Security* tab. This tab allows you to create signature verification configurtions. Choose *Create*.

22. In the resulting dialog, maintain the following fields:


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
    
    **AS2 Partner ID**
    
    </td>
    <td valign="top">
    
    Enter the ID of the AS2 Partner
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Alias**
    
    </td>
    <td valign="top">
    
    Maintain an alias for the configuration
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Signature**
    
    </td>
    <td valign="top">
    
    Select the signature mode for the configuration from the drop-down list
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Public Key Alias \(appears only when you choose the option *Trusted Certificate* for *Signature*\)
    
    </td>
    <td valign="top">
    
    Select a certificate from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Verify MIC\(MDN Only\)**
    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to enable the Message Integrity Check \(MIC\). This applies only for AS2 MDN.
    
    </td>
    </tr>
    </table>
    
23. Choose *Save*. You have now successfully created a communication partner.


