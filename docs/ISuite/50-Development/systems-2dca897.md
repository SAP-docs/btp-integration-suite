<!-- loio2dca897b0f684de698ba0339aeeba7dd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Systems

Create and maintain system-related configurations for your company or subsidiary.



## Context

*Systems* tab allows you to maintain the B2B standard details. You need this information to create agreements. Each agreement contains a specific B2B standard and conducts transactions based on the protocols provided by this B2B standard. To maintain the type systems in your agreement, you need to create and define them in the company profile or subsidiary.

In this tab, you create a system. Each system has a type system to define the B2B standard, and communication information to define your communication and adapter details for the system. Follow the procedure to maintain your system details.



## Procedure

1.  In your company profile, go to the *Systems* tab and choose *Create*.

2.  In the upcoming dialog, add the following system details:

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

    > ### Note:  
    > An alias is a user provided, tenant-independent identifier for artifacts that can be used to maintain referential integrity in cross-tenant use cases like transport. To know more, see [Understanding the Basic Concepts](../understanding-the-basic-concepts-74c068d.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Select the type of the system from the drop-down list.

    If you want to modify the system type details, choose :pencil2:.

    If your system type is not available in the list, choose :heavy_plus_sign: and enter the details of the new system, then choose *Apply*. The newly created system is now selected in the *Type* field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Purpose
    
    </td>
    <td valign="top">
    
    Select the purpose of the type system from the drop-down list. You can choose *Dev*, *Test*, or *Prod*. The value that you set here is picked up during the agreement activation to denote in the payload the purpose of the transaction.

    See [Payload Indicator in Integration Flow Message Processing](payload-indicator-in-integration-flow-message-processing-7f322c0.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Link
    
    </td>
    <td valign="top">
    
    Provide a link to the system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Provide a description for the system.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save* to create the system.

4.  You also need to configure the type system and communication channel details for the newly created company profile and hence its *Status* is set to *Incomplete*.

    > ### Note:  
    > To know more about type systems, see [Terminology for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/9c221b48799a4ce59367b0e3367f5a8f.html).

    To do so, select the newly created system and under the *Type Systems* tab, choose *Create Type System*.

5.  In the *Assign Type System Version\(s\)* dialog, select the *Name* and *Version* of the type system from the drop-down list.

    > ### Note:  
    > For **SOAP** and **IDoc** type systems, enter versions manually by selecting the checkbox *Input Version Manually* and maintaining the *Version* field.
    > 
    > For **cXML** type systems, the version you select must be the same as the value maintained for the `/cXML/@version` attribute in the incoming cXML payload. If the `/cXML/@version` attribute doesn’t exist, leave the version empty.

6.  Choose *Save*. The type system is added. Choose *Save* to update the system.

7.  Navigate to the *Communications* tab and choose *Create Communication*.

8.  Maintain the following fields:

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
    
    Enter a valid name for your communication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    Enter an alias for the communication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Provide a description.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Direction
    
    </td>
    <td valign="top">
    
    Choose whether the communication channel is a *Sender* or *Receiver*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter
    
    </td>
    <td valign="top">
    
    Select an adapter from the drop-down list.

    > ### Note:  
    > The following adapters are supported for *Sender* communication:
    > 
    > -   AS2
    > 
    > -   AS2 MDN
    > -   IDOC
    > -   SOAP 1.x
    > -   Process\_Direct
    > -   SFTP
    > 
    > The following adapters are supported adapters for *Receiver* communication:
    > 
    > -   AS2
    > 
    > -   IDOC
    > -   SAP RM
    > -   SOAP\_1.x
    > -   Process\_Direct
    > -   SFTP


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Account

    > ### Note:  
    > This field appears only when you choose *AS2* as the Sender adapter.


    
    </td>
    <td valign="top">
    
    Enter the user account that you have configured in Cloud Integration tenant for authorization.

    To know more, see [Partner Authorization](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/c0c9950003674d198e9e7ceda098053d.html).
    
    </td>
    </tr>
    </table>
    
9.  The *Connection* tab appears when you choose *SOAP\_1.x* or *SAP RM* or *IDOC* as the receiver adapter. Maintain the following fields:

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
    
    Enter the endpoint address at which Cloud Integration posts the outgoing message.
    
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
    
    IDoc Content Type
    
    </td>
    <td valign="top">
    
    If you selected `IDOC` as adapter, select the IDoc content type from the drop-down list.
    
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
    
10. The following tabs appear when you choose AS2 as the receiver adapter. Maintain the following fields:

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
    
    Recipient URL
    
    </td>
    <td valign="top">
    
    Enter the URL of the receiver system.
    
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
    
    Provide the credentials for basic authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias

    Only if you choose *Client Certificate* for authentication
    
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

    The file name can be composed of string constants and simple expressions like `${header.}`, `${property.}`, the predefined placeholder `${TIMESTAMP}` \(current timestamp\), and `${TIMESTAMP_WITH_MS}` \(current timestamp with milliseconds\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Append Timestamp
    
    </td>
    <td valign="top">
    
    Appends a timestamp at the end of the file name.

    > ### Note:  
    > This feature is deprecated and will be removed soon.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Include Millisecond
    
    </td>
    <td valign="top">
    
    Select this checkbox if you want milliseconds to be included the AS2 timestamp \(yyyyMMddHHmmssSSS\).

    > ### Note:  
    > This feature is deprecated and will be removed soon.


    
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
    
11. If you chose **Process Direct** as the receiver adapter, the *Connection* tab appears. Maintain the address for the adapter in the *Address* field.

12. If you select AS2 as the *Sender* adapter, two new fields appear:

    -   *Security Configuration Mode*: The value is set as *Channel* by default and cannot be edited.

    -   *User Account*: Enter the user account in this field.

    Maintain the following tabs:

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
    
    This field should be maintained in *Security* tab to sign the MDN on partner's request.
    
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

    \(Only if you chose *On-Premise* as the *Proxy Type*\)
    
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
    <tr>
    <td valign="top">
    
    Private Key Alias

    \(Only if you chose *Client Certificate* for authentication\)
    
    </td>
    <td valign="top">
    
    This field should be maintained in the *Security* tab for client certificate authentication.
    
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
    > You need to first maintain the Private Key Alias in the Cloud Integration Keystore.


    
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
        > If *Trusted Root Certificate* is selected, mention the public key alias immediate root certificate of the incoming message.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Public Key Alias \(Only if you have selected *Trusted Certificate* or *Trusted Root Certificate*\)
    
    </td>
    <td valign="top">
    
    Specify the public key alias to verify the signature of the AS2 message.

    > ### Note:  
    > You need to first maintain the certificates under the *Certificates* tab of the company profile.


    
    </td>
    </tr>
    </table>
    
13. The following tabs appear if you choose the SFTP sender adapter. Maintain the following fields:

    ****


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
    
    Directory
    
    </td>
    <td valign="top">
    
    Enter the file path at which the files should be read. The relative path is used to read the file from a directory.

    Example: `parentdirectory/childdirectory`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    File Name
    
    </td>
    <td valign="top">
    
    Enter the name of the file that should be read. You can use wildcards to specify which file in the specified directory is read.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    Enter the host name or IP address and port of the SFTP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Defines the proxy type to be used to connect to SFTP server. Select one of the following:

    -   Select *Internet* to connect directly to the SFTP server.
    -   Select *On-Premise* to connect to an on-premise SFTP server.

    See [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

    For more information on how to use the **On-Premise** option to connect to an on-premise SFTP server, see the SAP Community blog [Cloud Integration – How to Connect to an On-Premise SFTP Server via Cloud Connector](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fblogs.sap.com%2F2018%2F11%2F16%2Fcloud-integration-how-to-connect-to-an-on-premise-sftp-server-via-cloud-connector%2F).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID
    
    </td>
    <td valign="top">
    
    This option is available if the proxy type is **On-Premise**.

    To connect to a Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration of SAP BTP cockpit.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    This field specifies how Cloud Integration is authenticated when connecting to the SFTP server. Enter the ID of the user performing the file transfer.

    > ### Caution:  
    > The user name must only consists of the following characters:
    > 
    > `A-z`, `0-9`, `_` \(underscore\), `-` \(hyphen\), `/` \(slash\), `?` \(question mark\), `@` \(at\), `!` \(exclamation mark\), `$` \(dollar sign\), `'` \(apostrophe\), `( )` \(brackets\), `*` \(asterisk\), `+` \(plus sign\), `,` \(comma\), `;` \(semicolon\), `=` \(equality sign\), `.` \(dot\), `~` \(tilde\)
    > 
    > If any other characters are used, an attempt for anonymous login is made, which results in an error.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name
    
    </td>
    <td valign="top">
    
    If the authentication method is *User Name/Password* or *Dual*: Referenced credential name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Name
    
    </td>
    <td valign="top">
    
    If the authentication method is *Public Key*: ID of the user performing the file transfer .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias
    
    </td>
    <td valign="top">
    
    If the authentication method is *Public Key* or *Dual*: The alias used to identify the private key in the key store and communicate with the SFTP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Timeout \(in ms\)
    
    </td>
    <td valign="top">
    
    Maximum waiting time \(in milliseconds\) to contact the SFTP server while establishing a connection or performing a read operation.

    Default value: `10000`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Maximum Reconnect Attempts
    
    </td>
    <td valign="top">
    
    Maximum number of attempts allowed to reconnect to the SFTP server.

    Default value: `3`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Reconnect Delay \(in ms\)
    
    </td>
    <td valign="top">
    
    Waiting time \(in milliseconds\) that before attempting to reconnect to the remote SFTP server. Default value: 1000
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Automatically Disconnect
    
    </td>
    <td valign="top">
    
    Disconnects from the server after each poll.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Directory Stepwise
    
    </td>
    <td valign="top">
    
    Changes the directory levels one at a time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use Fast Exists Check
    
    </td>
    <td valign="top">
    
    If selected, the file exists check is performed on the SFTP server. If your server doesn't support this operation, switch back to client-side check.
    
    </td>
    </tr>
    </table>
    
14. The following tabs appear if you choose **SFTP receiver adapter**. Maintain the following fields:

    ****


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
    
    Directory
    
    </td>
    <td valign="top">
    
    File path to where the file should be written.

    Example: `parentdirectory/childdirectory`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    File Name
    
    </td>
    <td valign="top">
    
    Name of the file to be written. The filename can be composed of string constants and simple expressions like `${header.<header-name>}`, `${property.<property-name>}`, the predefined placeholder `${TIMESTAMP}` \(current timestamp\) and `${TIMESTAMP_WITH_MS}` \(current timestamp with milliseconds\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    Host name or IP address and port of the SFTP server
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Specify the proxy type to be used:

    -   Select *Internet* to connect directly to the SFTP server.
    -   Select *On-Premise* to connect to on-premise system.

    See [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

    For more information on how to use the **On-Premise** option to connect to an on-premise SFTP server, see the SAP Community blog [Cloud Integration – How to Connect to an On-Premise SFTP Server via Cloud Connector](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fblogs.sap.com%2F2018%2F11%2F16%2Fcloud-integration-how-to-connect-to-an-on-premise-sftp-server-via-cloud-connector%2F).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID
    
    </td>
    <td valign="top">
    
    This option is available if the proxy type is *On-Premise*.

    To connect to a Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration of SAP BTP cockpit.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    This field specifies how the user is authenticated. Enter the ID of the user performing the file transfer.

    > ### Caution:  
    > The user name must only consists of the following characters:
    > 
    > `A-z`, `0-9`, `_` \(underscore\), `-` \(hyphen\), `/` \(slash\), `?` \(question mark\), `@` \(at\), `!` \(exclamation mark\), `$` \(dollar sign\), `'` \(apostrophe\), `( )` \(brackets\), `*` \(asterisk\), `+` \(plus sign\), `,` \(comma\), `;` \(semicolon\), `=` \(equality sign\), `.` \(dot\), `~` \(tilde\)
    > 
    > If any other characters are used, an attempt for anonymous login is made, which results in an error.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential name
    
    </td>
    <td valign="top">
    
    If the authentication method is **User Name/Password** or **Dual**: Referenced credential name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Name
    
    </td>
    <td valign="top">
    
    If the authentication method is **Public Key**: ID of the user performing the file transfer
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Private Key Alias
    
    </td>
    <td valign="top">
    
    If the authentication method is **Public Key** or **Dual**: The alias used to identify the private key in the keystore to communicate with the SFTP server
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Timeout \(in ms\)
    
    </td>
    <td valign="top">
    
    Maximum waiting time taken to contact the SFTP server while establishing connection or performing a read operation.

    Default value: `10000`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Maximum Reconnect Attempts
    
    </td>
    <td valign="top">
    
    Maximum number of attempts allowed to reconnect to the SFTP server.

    Default value: `3`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Reconnect Delay \(in ms\)
    
    </td>
    <td valign="top">
    
    Time period to wait before attempting to reconnect to the remote SFTP server.

    Default value: `1000`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Automatically Disconnect
    
    </td>
    <td valign="top">
    
    Disconnect from the SFTP server after each message processing
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Directories Stepwise
    
    </td>
    <td valign="top">
    
    Changes directory levels one at a time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Create Directories
    
    </td>
    <td valign="top">
    
    Creates missing directory levels automatically as provided in the file's path name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Flatten File names
    
    </td>
    <td valign="top">
    
    Flattens the file path by removing the directory levels. If specified, only the file names are considered, and the files are written into a single directory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Handling for Existing Files
    
    </td>
    <td valign="top">
    
    If a file already exists in the target, it allows to:

    -   **Override**: Replace the existing file content with the new one.
    -   **Append**: Add the new file content to the end of the existing one.
    -   **Fail**: Do not perform any action and raise a failure.
    -   **Ignore**: Do not perform any action.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use Fast Exists Check
    
    </td>
    <td valign="top">
    
    If selected, the file exists check is performed on the SFTP server. If your server doesn't support this operation, switch back to client-side check.
    
    </td>
    </tr>
    </table>
    
15. Choose *Save*.

    > ### Note:  
    > To complete the system setup, you need to maintain both *Sender* and *Receiver* communication channel details.
    > 
    > After you maintained the necessary details, the *Status* of the system is set to *Completed*.




## Next Steps

Next, you need to maintain the certificates for your profile. Navigate to the *Certificates* tab and follow the procedure mentioned in [Certificates](certificates-b64fcf2.md).

