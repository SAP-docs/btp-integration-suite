<!-- loio912c3d3b9ab84e309544aaffe3d02fa3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Systems

Create and maintain system related configuration for your partner profile.



## Context

*Systems* tab allows you to maintain the B2B standard details. You need this information to create agreements. Each agreement contains a specific B2B standard and conducts transactions based on the protocols provided by this B2B standard. In order to maintain the type systems in you agreement, you need to create and define them in the partner profile.



## Procedure

1.  Navigate to the *Systems* tab.

2.  Choose *Create* to add the following system details:

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
    
3.  Choose *Save*. The system gets created successfully.

4.  You also need to configure the type system and communication channel details for the newly created company profile and hence its *Status* is set to *Incomplete*.

    > ### Note:  
    > To know more about type systems, see [Terminology for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/9c221b48799a4ce59367b0e3367f5a8f.html)

5.  To do so, select the newly created system and under the *Type System* tab, choose *Create Type System*.

6.  In the *Create Type System* dialog, select the *Name* and *Version* of the type system from the drop-down list.

    > ### Note:  
    > For **SOAP** and **IDOC** type systems, you can enter versions manually by selecting the checkbox *Input Version Manually* and maintaing the *Version* field.

7.  Choose *Save*. The type system is added successfully. Choose *Save* to update the system.

8.  Navigate to the *Communication* tab and choose *Create*.

9.  Maintain the following fields:

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
    > -   Process\_Direct
    > 
    > The supported adapters for *Receiver* communication are:
    > 
    > -   AS2
    > 
    > -   IDOC
    > -   SAP RM
    > -   SOAP\_1.x
    > -   Process\_Direct


    
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
    
10. The *Connection* tab appears when you choose *SOAP\_1.x* or *SAP RM* or *IDOC* as the receiver adapter. Maintain the following fields:

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
    
11. The following tabs appear when you choose AS2 receiver adapter. Maintain the following fields:

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
    
    Include Millisecond
    
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
    
12. If you chose **Process Direct** as the receiver adapter, the *Connection* tab will appear. Maintain the address for the adapter in the *Address* field.

13. If you select AS2 as the *Sender* adapter, two new fields appear:

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
    
14. Choose *Save*.

    > ### Note:  
    > You need to maintain both *Sender* and *Receiver* communication channel details to complete the system set-up.
    > 
    > After maintaining the necessary details, the *Status* of the System is set to *Completed*.

15. For the next step, see [Certificates](certificates-5c4a01a.md).


