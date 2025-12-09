<!-- loio53d5c974dcc446eeaf9eb207033fd813 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuring Service Interface

A service interface can be defined by using [Message Types](working-with-data-types-message-types-cf1d397.md). This two-layer structure uses Web Service Description Language \(WSDL\) and is oriented towards maximum reusability. To handle application-specific errors, you have the option of using fault-message types.

Cloud Integration allows you to view and edit your service interfaces.



<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_dbn_mnf_qfc"/>

## Overview

On this tab, you can view and edit the following general details of a service interface:

**General Information**


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of the artifact.

</td>
</tr>
<tr>
<td valign="top">

*ID*

</td>
<td valign="top">

Unique ID of the artifact.

</td>
</tr>
<tr>
<td valign="top">

*Target Namespace*

</td>
<td valign="top">

Displays the namespace to which the service interface belongs to or where it's created.

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Version of the artifact imported from ES repository.

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Additional details captured when the artifact was created in the ES repository.

</td>
</tr>
</table>

**Attributes Information**


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Category*

</td>
<td valign="top">

You can choose one of the following:

-   *Inbound* \(Provider Role\): Used to implement a service in an application system, which can be called by a user.
-   *Outbound* \(Consumer Role\): Used to call a service of a provider. To do so, you require the outbound service interface that matches your inbound service interface.
-   *Abstract*: Used to exchange messages with integration process.

    > ### Note:  
    > This category is supported for the artifacts imported from ES Repository.




</td>
</tr>
<tr>
<td valign="top">

*Interface Pattern*

</td>
<td valign="top">

The interface pattern determines how an integration developer designs communications in the back-end. You can choose one of the following:

-   *Stateless*: The messaging runtime does not support the saving of a status at the provider once the messaging runtime has completed the message exchange successfully.
-   *Stateless \(XI30-Compatible\)*: Use this stateless pattern to continue using all existing protocols \(up to SAP NetWeaver 2004s\) in the back end that were developed on the basis of message interfaces.

    Additionally, you can enable the point-to-point communication for this interface pattern.

-   *Stateful*: The messaging runtime supports the saving of a status at the provider once the messaging runtime has completed the message exchange successfully.
-   *TUCC&C/C*: Communication is only suitable for scenarios within a system landscape and is based on protocols for synchronous and asynchronous communication.



</td>
</tr>
<tr>
<td valign="top">

*Security Profile*

</td>
<td valign="top">

These values influence the behavior during implementation of this service definition. If the interface pattern is Stateless \(XI30-compatible\), you can choose one of the following:

-   Basic - Basic Authentication using user ID and password and no transport security.
-   Strong - Strong Authentication \(SSL or SSO\) and transport security.

    > ### Note:  
    > The *Security Profile* field is available only if the *Point- to-Point enabled* checkbox is selected.


If interface pattern is `Stateful` or `Stateless`, you can choose one of the following:

-   `None`: No Authentication and no transport security.
-   `Low`: Basic Authentication using user ID and password and no transport security.
-   `Medium`: Basic Authentication using user ID and password and transport security.
-   `High`: Strong Authentication \(SSL or SSO\) and transport security.



</td>
</tr>
</table>

**ES Repository Information**


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Software Component Version*

</td>
<td valign="top">

For artifacts imported from ES Repository, you can view the software component version to which the artifact belongs to in ES Repository.

</td>
</tr>
</table>

**Administrative Data**


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Created by and Modified by

</td>
<td valign="top">

Displays the identity of the user who imported and last modified the service interface along with respective dates.

</td>
</tr>
</table>



<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_dsb_3qf_qfc"/>

## References

The structure of the data to be exchanged is defined by the reference to a message schema. You can find following tabs:

-   *Local*: You can upload the WSDLs or XSDs for the respective service interface artifact. These can only be used for the exchange messages in the operations of this artifact.

    To add files from the file system:

    1.  Choose *Add* and select WSDL or XSD as file type.

    2.  Select *File System* as the source.

    3.  Choose *Browse* to select one or more files from the file system.

    4.  Choose *Add* to upload the files.

        > ### Note:  
        > You can add multiple resources from the file system, but you can't add multiple archive \(\*.zip\) files.



-   *Global*: You can select the message type or fault message type artifact available in your tenant. These artifacts maybe from other packages as well and can be re-used in other artifacts like a message mapping etc.

    To add files from the file system:

    1.  Choose *Add References* and select message type or fault message type.

    2.  Select one or more integration packages from the *Package* drop down.

        You will find a list of available reusable artifacts from the selected packages.

    3.  Select one or more artifacts from the table.

    4.  Choose *OK* to create reference for the selected reusable artifacts.





<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_az2_lqf_qfc"/>

## Definition

You can create and edit the details of various source and target operations defined for the service interface in this tab.

The message exchange happens at runtime. The operation that sends a message is also referred to as a source operation, and the operation that receives a message as a target operation.

Follow these steps to add and configure an operation:

1.  Choose :heavy_plus_sign: to add a new operation.

2.  Specify its name and choose *Add*.

    A new operation is added to the list.

3.  Choose the operation to configure. Refer to the details below:

    **Elements in Definition**


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
    
    Release State
    
    </td>
    <td valign="top">
    
    Depicts the development status of the object. The release state of the object determines whether the customer can or cannot use the object, and whether restrictions apply. You can choose one of the following:

    -   *Not Released*: Objects with this release state have not yet been released by SAP and cannot be used by customers in the current release
    -   *Released with Restrictions*: The stability of these artifacts are not guaranteed.
    -   *Released*: Ready to use.
    -   *Deprecated*: Objects in this state can still be used in the release in which they were set to Deprecated.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operation Pattern
    
    </td>
    <td valign="top">
    
    A service interface can have multiple operations. Depending on the interface pattern selected from the overview tab, the operation pattern options vary. See [Table](configuring-service-interface-53d5c97.md#loio53d5c974dcc446eeaf9eb207033fd813__table_akr_f1r_3hc)

    You can choose one of the following:

    -   *Normal*

    -   *Commit*

    -   *Rollback*

    -   *Compensate*

    -   *Confirm*

    -   *Tentative Update*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Mode
    
    </td>
    <td valign="top">
    
    Displays whether the communication mode of the operation. You can choose one of the following:

    -   *Asynchronous*: This communication mode with the quality of service Exactly Once \(In Order\) \(EOIO\) guarantees that a message is delivered once even after system crash. This mode does not support response [Role](configuring-service-interface-53d5c97.md#loio53d5c974dcc446eeaf9eb207033fd813__row_lv4_qvg_hhc).
    -   *Synchronous*: This mode is better suited if the continuance of a communication depends on the results of a service call. This mode supports all the message [Role](configuring-service-interface-53d5c97.md#loio53d5c974dcc446eeaf9eb207033fd813__row_lv4_qvg_hhc).
        -   Idempotent: An idempotent operation yields the same result after the operation is applied multiple times. When an error occurs in the communication between consumer and provider, the consumer tries to send the same message again. If the service is implemented on the provider with the idempotency functionality, then the provider can handle the message correctly. For example, if the provider has already sent a response and the error occurred after sending the response, the provider does not handle the request the second time, but just sends the stored message again.



    
    </td>
    </tr>
    </table>
    
    Based on the selected modes for the respective operation pattern, you can see the required message roles.

4.  To assign the references for each role, choose <span class="SAP-icons-V5"></span> in the *Name* column, and on the *Local Resources* or *Global Resources* tab, select the available resources or artifacts.

    The below details are automatically populated for the selected resource:

    **Elements in Definition**


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
    
    Role
    
    </td>
    <td valign="top">
    
    Message types are referenced for three different roles for each operation:

    Request \(asynchronous and synchronous communication\): The request is the message that the consumer sends - using an operation in the outbound-service-interface - to a corresponding operation in the inbound-service-interface.

    Response \(synchronous communication only\): The response is the direct response that the consumer waits for after the request message has been sent. The message is sent from the provider \(inbound-service-interface\) to the consumer \(outbound-service-interface\).

    Fault \(asynchronous and synchronous communication\): Message that is either sent to the consumer \(synchronous\) or persisted for monitoring \(asynchronous\) if an error occurs at the provider.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Displays whether the referenced artifact is a [message type](working-with-data-types-message-types-cf1d397.md), fault message type, WSDL, or XSD.

    Fault Message Type: This is a special message type that is used in service interface. These are designed for application-specific errors that occur at the provider \(inbound side\) and are reported back to the sender or persisted in monitoring.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package Name
    
    </td>
    <td valign="top">
    
    Displays the package name of the referenced artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace
    
    </td>
    <td valign="top">
    
    Displays the namespace of the referenced artifact.
    
    </td>
    </tr>
    </table>
    
5.  Optional, in the *Messages* section, you can choose *Add Fault* to add fault messages and assign resources.


The following table shows the supported combinations of service interface categories, interface patterns, operation patterns, operation modes, and security profiles:

****


<table>
<tr>
<th valign="top">

Category

</th>
<th valign="top">

Interface Pattern

</th>
<th valign="top">

Operation Pattern

</th>
<th valign="top">

Operation Mode

</th>
<th valign="top">

Security Profile

</th>
</tr>
<tr>
<td valign="top" rowspan="9">

Inbound and Outbound

</td>
<td valign="top">

Stateless

</td>
<td valign="top">

Normal

</td>
<td valign="top">

Synchronous and Asynchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Stateless \(XI30-Compatible\)

</td>
<td valign="top">

Normal

</td>
<td valign="top">

Synchronous and Asynchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Stateful

</td>
<td valign="top">

Normal

</td>
<td valign="top">

Synchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Commit

</td>
<td valign="top">

Synchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Rollback

</td>
<td valign="top">

Synchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

TU&C/C

</td>
<td valign="top">

Normal

</td>
<td valign="top">

Synchronous and Asynchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Tentative update

</td>
<td valign="top">

Synchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Confirm

</td>
<td valign="top">

Asynchronous

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Compensate

</td>
<td valign="top">

Asynchronous

</td>
<td valign="top">

All

</td>
</tr>
</table>



<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_y3f_mqf_qfc"/>

## WSDL

In Web Services Description Language \(WSDL\), the structure and format of the data exchanged in messages are defined using XML Schema Definition \(XSD\).

