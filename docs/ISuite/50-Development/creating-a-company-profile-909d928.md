<!-- loio909d9282770e40be8dbc1904948b8627 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Company Profile

The term *Company* is used to refer a specific kind of trading partner. This trading partner represents the user \(owner\) of the SAP Integration Suite system.

Follow the next procedure to create a company profile.



<a name="loio909d9282770e40be8dbc1904948b8627__section_hbc_dfs_kqb"/>

## Overview

1.  Log on to your Integration Suite .
2.  Choose *Design* \> *B2B Scenarios*.
3.  Select the tab *Company Profile* and choose *Create Profile*.

    > ### Note:  
    > The application can have only one company profile.

4.  Open the *Overview* tab, maintain the following fields after the *Details* section.

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
    
    The web link to access your company.
    
    </td>
    </tr>
    </table>
    
5.  You can also provide the address of your company in the *Address* section.
6.  Choose *Save*.

    > ### Note:  
    > The *Logo* field is disabled initially. You can upload an image after saving the before mentioned entries. To do so, choose *Edit* and select *Browse* to search and upload your company logo.




<a name="loio909d9282770e40be8dbc1904948b8627__section_cyv_vlc_bzb"/>

## Contacts

1.  Navigate to the *Contacts* tab.
2.  Choose *Create* and provide the following information.

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
    
    A valid first name of the contact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Second Name
    
    </td>
    <td valign="top">
    
    Provide the second/last name of the contact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role
    
    </td>
    <td valign="top">
    
    The role of the contact in the company.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EMail
    
    </td>
    <td valign="top">
    
    A valid email ID of the contact. You can add multiple entries by selecting the :heavy_plus_sign: button.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Phone
    
    </td>
    <td valign="top">
    
    A valid phone number of the contact. You can add multiple entries by selecting the :heavy_plus_sign: button.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    The address of the contact.
    
    </td>
    </tr>
    </table>
    
3.  Check the checkbox *Preferred Contact* if you want this newly created contact to be the preferred contact for communication. This contact details will get displayed in the company profile *Overview*.
4.  Set the *Preferred Email* and *Preferred Phone* using the drop-down menu.
5.  Choose *Save*. The contact gets created. Choose *Save* at the end of the screen to update the company profile.
6.  You can also modify or delete the contact details using the :pencil2: and :wastebasket: buttons respectively.



<a name="loio909d9282770e40be8dbc1904948b8627__section_bzy_qlc_bzb"/>

## Identifiers

1.  Navigate to the *Identifiers* tab. The tab consists of two sections:
    -   *Single Identifiers*: These are individual identifiers that have their own type system, scheme and organization etc. If you want to create a single identifier, choose *Create* provided above the *Single Identifiers* table and follow from Step 2 below.

    -   *Identifier Groups*: These are identifier groups that have a common Alias, Type System, Agency and Scheme. If you want to create an identifier group, choose *Create* provided above the *Identifiers Groups* table and follow the instructions from Step 4 below.

2.  For Single Identifier, enter the following details.

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
    
    Provide a valid ID for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    Enter an alias for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System
    
    </td>
    <td valign="top">
    
    Choose a type system from the drop-down list.

    > ### Note:  
    > -   For *GS1 XML* type system, you must maintain the contact details in the *Contacts* tab.
    > 
    > -   For *Tradacoms* type system for the identifier, the field *Identification* is mandatory. If the sender payload contains both *Identification* and *Name*, the integration flow will consider only *Identification* for the computed Partner Directory ID.
    > 
    >     The system ASSEMBLY will use Company profile's *Short Name* for the *Identification Name*
    > 
    >     Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme
    
    </td>
    <td valign="top">
    
    Choose a scheme from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Agency
    
    </td>
    <td valign="top">
    
    Provide the agency name and code in their respective fields.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.
4.  For Identifier Group, maintain the following details:

    **Create Identifier Group**


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
    
    Group Name
    
    </td>
    <td valign="top">
    
    Provide a valid name for the identifier group.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    Enter an alias for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System
    
    </td>
    <td valign="top">
    
    Choose a type system from the drop-down list.

    > ### Note:  
    > -   For *GS1 XML* type system, you must maintain the contact details in the *Contacts* tab.
    > 
    > -   For *Tradacoms* type system for the identifier, the field *Identification* is mandatory. If the sender payload contains both *Identification* and *Name*, the integration flow will consider only *Identification* for the computed Partner Directory ID.
    > 
    >     The system ASSEMBLY will use Company profile's *Short Name* for the *Identification Name*
    > 
    >     Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme
    
    </td>
    <td valign="top">
    
    Choose a scheme from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Agency
    
    </td>
    <td valign="top">
    
    Provide the agency name and code in their respective fields.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*. The identifier group is created successfully. You need to now add identifiers to it.
6.  Open the identifier group from the *Identifier Groups* table.
7.  Choose *Edit* to edit the details of the group.
8.  Select *Add* above the *Identifiers in Group* to add idenifiers to this group.
9.  Maintain the values for *Identification* and *Sub-Organization* fields and choose *Save*.
10. Choose *Activate* to activate the group and publish its identifier details into the partner directory. This step just publishes the content and the identifiers would take effect only if any agreement using the identifier group gets activated.
11. If you make any changes after the activation of the group and want to push the latest changes to the Partner Directory, save your changes and choose *Update*.



<a name="loio909d9282770e40be8dbc1904948b8627__section_ejh_llc_bzb"/>

## Business Context

1.  Navigate to *Business Context*.
2.  Choose *Edit* and enter the following information.

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
    
    Business Process
    
    </td>
    <td valign="top">
    
    Select the business process from the drop-down list. You can select more than one entry.
    
    </td>
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
    
    Choose the country details from the drop-down list.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.



<a name="loio909d9282770e40be8dbc1904948b8627__section_d1v_blc_bzb"/>

## Systems

1.  Navigate to the *System* tab.
2.  Choose *Create* to add the following system details.

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
    > An Alias is a user provided, tenant independent identifier for artifacts, that can be used to maintain referential integrity in cross tenant use cases like transport. To know more, see [Understanding the Basic Concepts](understanding-the-basic-concepts-74c068d.md)
    > 
    > .


    
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

    To know more, see [Payload Indicator in Integration Flow Message Processing](payload-indicator-in-integration-flow-message-processing-7f322c0.md).
    
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
    
3.  Choose *Save*. The system gets created successfully.
4.  You also need to configure the type system and communication channel details for the newly created company profile and hence its *Status* is set to *Incomplete*.

    > ### Note:  
    > To know more about type systems, see [Terminology for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/9c221b48799a4ce59367b0e3367f5a8f.html).

5.  To do so, select the newly created system and under the *Type System* tab, choose *Create*.
6.  In the *Create Type System* dialog, select the *Name* and *Version* of the type system from the drop-down list.
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
    
12. If you select AS2 as the *Sender* adapter, two new fields appear:

    -   *Security Configuration Mode*: The value is set as *Channel* by default.

    -   *User Account*: Enter the user account in this field.

    The following tabs appear when you choose AS2 as the sender adapter. Maintain the following fields:

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
    
    This field should be maintained when opening the *Security* tab to sign the MDN on partner's request.
    
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
    
    </td>
    <td valign="top">
    
    This field should be maintained when opening the *Security* tab for client certificate authentication.
    
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
    
    Public Key Alias \(Only if you have selected *Trusted Certificate*\)
    
    </td>
    <td valign="top">
    
    Specify the public key alias to verify the signature of the AS2 message.

    > ### Note:  
    > You need to first maintain the certificates under the *Certificates* tab of the company profile.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Public Key Aliases \(Only if you have selected *Trusted Root Certificate*\)
    
    </td>
    <td valign="top">
    
    Specify the public key aliases to verify the signature of the AS2 message.

    > ### Note:  
    > You need to first maintain the certificates under the *Certificates* tab of the company profile.


    
    </td>
    </tr>
    </table>
    
13. If you select *Process\_Direct* as the receiver adapter, the *Connection* tab appears with the *Address* field.
14. Enter the address value for the adapter in the *Address* field.
15. Choose *Save*.

    > ### Note:  
    > You need to maintain both *Sender* and *Receiver* communication channel details to complete the system set-up.
    > 
    > After maintaining the necessary details, the *Status* of the System is set to *Completed*.




<a name="loio909d9282770e40be8dbc1904948b8627__section_inp_rkc_bzb"/>

## Certificates

1.  Navigate to the *Certificate* tab and choose *Create*.
2.  Maintain the following details:

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
    
    Provide an alias name for the certificate.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    File
    
    </td>
    <td valign="top">
    
    Browse and upload the certificate.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Add*. The certificate gets added successfully. You can perform other actions on this certificate using the <span class="SAP-icons-V5"></span> button.



<a name="loio909d9282770e40be8dbc1904948b8627__section_dtn_hkc_bzb"/>

## Parameters

The application also allows you to maintain Dynamic Parameters selecting the company profile. These parameters can be helpful when

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


To do so, you need to create/upload the parameters to your company profile.

1.  Navigate to the *Parameters* tab of the company profile.

2.  You can create or import dynamic parameters in the system.

3.  If you chose *Create*:
    1.  Enter a key in the *Parameter Key* field.

    2.  Enter the value for the key in the *Value* field.
    3.  Choose *Save*. The parameter is now successfully added to the list.

4.  If you chose *Import*:

    1.  In the *Import File* dialog, choose *Browse* to select and upload a csv file.
    2.  Choose a type of the csv file under the *Type* field.
    3.  Select the field seperator of the csv file from the drop-down list of the field *Field Seperator in CSV*.
    4.  Choose *Next*. The next screen displays a preview of the parameters in the csv file.
    5.  Choose *Import*. The parameters are now successfully added to the company profile.


You have now successfully created a company profile and you can view the details when selecting the *Company Profile* tab. You can also review the administrative details when selecting the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date



<a name="loio909d9282770e40be8dbc1904948b8627__section_lzw_nkc_bzb"/>

## Security

When you use AS2 adapters in your agreements, you need to maintain few decryption configurations. To do so,

1.  Navigate to the *Security* tab and choose *Create*.

2.  Maintain the following fields:
    1.  *User Account*: Enter the user account name.

    2.  *Alias*: Maintain an alias for the configuration.
    3.  *Private Key Alias*: Enter a Private Key Alias for the configuration.

3.  Choose *Save* after maintaining all the fields. These configurations should be activated in order to be used in an Agreement. Select the toggle button after the *Activation Status* header to activate your configuration.



<a name="loio909d9282770e40be8dbc1904948b8627__section_s1f_cqk_jzb"/>

## Number Ranges

While sending out a document in case of EDI processing, a unique interchange number must be added to each document. In order to add such an interchange number you can use the Number Ranges. The *Number Ranges* tab allows you to create an alias for the existing number ranges created in the *Monitor* tab. To know how to create and define number ranges, see [Managing Number Ranges](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-number-ranges). Follow the procedure below to create an alias for the number range:

1.  Navigate to the *Number Ranges* tab.

2.  Choose *Add*.
3.  In the resulting dialog, select a number range from the list for the *Number Ranges* field.

    > ### Note:  
    > The field displays the number ranges that are created in the *Monitor* tab for integrations. To know more, see [Managing Number Ranges](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-number-ranges).

4.  Enter an alias name for the number range in the *Name* field and choose *Save*.

**Related Information**  


[Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md "A trading partner is a company, organization, or a subsidiary that conducts e-business (B2B) with other companies, organizations or subsidiaries.")

