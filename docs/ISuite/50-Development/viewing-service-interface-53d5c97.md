<!-- loio53d5c974dcc446eeaf9eb207033fd813 -->

# Viewing Service Interface

A service interface can be defined by using [message types and data types](working-with-data-types-message-types-cf1d397.md). This two-layer structure uses Web Service Description Language \(WSDL\) and is oriented towards maximum reusability. To handle application-specific errors, you have the option of using fault-message types.

Cloud Integration allows you to view your service interfaces.



<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_dbn_mnf_qfc"/>

## Overview

From Cloud Integration Web UI, you can view the following general details of a service interface:

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

Additonal details captured when the artifact was created in the ES repository.

</td>
</tr>
</table>

**Attributes Infomation**


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

-   *Inbound*\(Provider Role\): Used to implement a service in an application system, which can be called by a user.
-   *Outbound*\(Consumer Role\): Used to call a service of a provider. To do so, you require the outbound service interface that matches your inbound service interface.
-   *Abstract*: Used to exchange messages with integration process.



</td>
</tr>
<tr>
<td valign="top">

*Interface Pattern*

\(point-to-point\)

</td>
<td valign="top">

The interface pattern determines how an integration developer designs communications in the back-end. Following are the type of communications that can be executed:

-   Stateless communication means that the messaging runtime does not support the saving of a status at the provider once the messaging runtime has completed the message exchange successfully.
-   Stateless \(XI30-Compatible\): Use this stateless pattern to continue using all existing protocols \(up to SAP NetWeaver 2004s\) in the back end that were developed on the basis of message interfaces.
-   Stateful communication means that the messaging runtime supports the saving of a status at the provider once the messaging runtime has completed the message exchange successfully.
-   TU&C/C communication is only suitable for scenarios within a system landscape and is based on protocols for synchronous and asynchronous communication.



</td>
</tr>
<tr>
<td valign="top">

*Security Profile*

</td>
<td valign="top">

These values influence the behavior during implementation of this service definition. If the interface pattern is Stateless \(XI30-compatible\), following values are possible:

-   Basic - Basic Authentication using user ID and password and no transport security.
-   Strong - Strong Authentication \(SSL or SSO\) and transport security.

    > ### Note:  
    > The *Security Profile* field is available only if the *Point- to-Point* enabled checkbox is enabled.


If interface pattern is `Stateful`, `Stateless`, or , following values may appear:

-   `No`: No Authentication and no transport security.
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

Displays the software component version to which the data type belongs to in ES repository.

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

The structure of the data to be exchanged is defined by the reference to a message schema. You can find following two tabs:

-   *Local*: Shows the WSDLs uploaded for the respective service interface artifact. These can only be used for the excange messages in the operations of this artifact.
-   *Global*: Shows the Message Type artifact availabel in your tenant. These artifacts maybe from other packages as well and can be re-used in other ertifacts like a message mapping etc.



<a name="loio53d5c974dcc446eeaf9eb207033fd813__section_az2_lqf_qfc"/>

## Definition

You can view the details of various source and target operations defined for the service interface in this tab.

The message exchange happens at runtime. The operation that sends a message is also referred to as a source operation, and the operation that receives a message as a target operation.

Choose an *Operation* to view its defiition.

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

Depicts the development status of the object. The release state of the object determines whether the customer can or cannot use the object, and whether restrictions apply.

-   Not Released: Objects with this release state have not yet been released by SAP and cannot be used by customers in the current release
-   Released with Restrictions: The stability of these artifcats are not guranteed.
-   Released: Ready to use.
-   Deprecated: Objects in this state can still be used in the release in which they were set to Deprecated.



</td>
</tr>
<tr>
<td valign="top">

Operation Pattern

</td>
<td valign="top">

A service interface can have multiple operations. Depending on the interface pattern, the operation pattern options vary.

Available operation patterns for service interface include normal, commit, rollback, compensate, tentative-update, and confirm.

</td>
</tr>
<tr>
<td valign="top">

Mode

</td>
<td valign="top">

Dsiplays whether the communication mode of the operation is synchronous or asynchronous.

-   Asynchronous: This communication mode with the quality of service Exactly Once \(In Order\) \(EOIO\) guarantees that a message is delivered once even after system crash. This mode does not support response [role.](viewing-service-interface-53d5c97.md#loio53d5c974dcc446eeaf9eb207033fd813__row_u4q_bqz_ggc)
-   Synchronous: This mode is better suited if the continuance of a communication depends on the results of a service call. This mode supports all the message [role.](viewing-service-interface-53d5c97.md#loio53d5c974dcc446eeaf9eb207033fd813__row_u4q_bqz_ggc).
    -   Idempotent: An idempotent operation yields the same result after the operation is applied multiple times.When an error occurs in the communication between consumer and provider, the consumer tries to send the same message again. If the service is implemented on the provider with the idempotency functionality, then the provider can handle the message correctly. For example, if the provider has already sent a response and the error occurred after sending the response, the provider does not handle the request the second time, but just sends the stored message again.




</td>
</tr>
<tr>
<td valign="top" colspan="2">

Messages: This section displays the references and operations added to each operation.

</td>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays if the referenced artifact is *Local* or *Global*.

Local references are WSDLs whereas the Global references are the artifacts available in the integration pacakges of your tenant.

The other fields *Role* *Type* *Package Name* and *Namespace* display the details of the referenced artifacts.

</td>
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

Displays whether the referenced artifact is message type, data type or fault message type.

-   Date Type and Message Type: See [Working with Data Types & Message Types](working-with-data-types-message-types-cf1d397.md)
-   Fault Message Type is a special message type that is used in service interface. These are designed for application-specific errors that occur at the provider \(inbound side\) and are reported back to the sender or persisted in monitoring.



</td>
</tr>
<tr>
<td valign="top">

Package Name

</td>
<td valign="top">

Displays the package name of the refereced artifact.

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

To understand the available combination of service interface category, interface pattern, operatin patterjn, modes, and message types, se the following table:

**Category, Interface Pattern, Operations**


<table>
<tr>
<th valign="top">

Category

</th>
<th valign="top">

Interface Pattern

</th>
<th valign="top">

Operation Patter

</th>
<th valign="top">

Opeeration Mode

</th>
<th valign="top">

Security Profile

</th>
</tr>
<tr>
<td valign="top">

 

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

 

</td>
<td valign="top">

Stateless \(XI 3.0 compatible\)

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

 

</td>
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

 

</td>
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

 

</td>
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
<td valign="top">

 

</td>
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

 

</td>
<td valign="top">

Tentative-update

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

 

</td>
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

 

</td>
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

