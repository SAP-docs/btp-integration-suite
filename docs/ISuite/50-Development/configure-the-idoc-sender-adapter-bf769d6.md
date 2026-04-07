<!-- loiobf769d68d95b458d87290dd2d37024b3 -->

# Configure the IDoc Sender Adapter

The IDoc sender adapter enables SAP Integration Suite to receive Intermediate Document \(IDoc\) messages from a sender.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – select the adapter and choose *Update Version* from the property sheet. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

The IDoc sender adapter in Cloud Integration supports both Exactly Once and Exactly Once In Order. Which Quality of Service is used depends on how the IDoc communication is configured in the sending system.

-   For Exactly Once In Order, the IDoc sender adapter sets the headers `SapPlainSoapQoS` and `SapPlainSoapQueueId` based on the IDoc control header `ARCKEY`, which can be used within the integration flow to model the message orchestration. Note that these headers are not set for the Exactly Once quality of service.
-   The IDoc sender adapter saves the protocol-specific ID in the header `SapMessageId`.

> ### Note:  
> For Exactly Once In Order delivery, ensure that IDocs are sent in the sequence in which they were created and that the sequence is preserved when a message goes into an error. As a prerequisite, apply the SAP note [3519275](https://me.sap.com/notes/3519275) in the sending system.



<a name="loiobf769d68d95b458d87290dd2d37024b3__section_ef4_zd1_sgb"/>

## Supported Headers

Header `SapAuthenticatedUserName` contains the user name of the client that calls the integration flow.

The following specific headers are set by the IDoc sender adapter and can be used in the subsequent steps of the integration flow.

-   `SapIDocType`

-   `SapIDocTransferId` 

-   `SapIDocDbId` 

-   `SapIDocContentType`
-   `SapIdocSoapNamespace`

More information: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



> ### Tip:  
> The adapter supports processing of composite \(bulk\) messages if the composite message consists of individual messages with the same message type.
> 
> If a composite message is processed, the header `SapIDocTransferId` contains the ID of the first IDoc only. If you like to access all transfer IDs, you need to read the payload using an XPath expression \(for example, in a *Content Modifier* step\).



<a name="loiobf769d68d95b458d87290dd2d37024b3__section_rj4_xd1_sgb"/>

## Configuring the Adapter

Once you have created a sender channel and selected the IDoc adapter, you can configure the following attributes. To change the configurations, you need to configure a new channel.

The *General* tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameters

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Relative endpoint address on which Cloud Integration can be reached by incoming requests, for example, `/GetEmployeeDetails`.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Invalid XML Character Handling

</td>
<td valign="top">

Select how to handle XML documents containing characters which are not valid in XML version 1.0/1.1. Depending on the XML version of the source message, the adapter checks the characters against the respective range allowed. Choose between the following options:

-   *Throw Error*: An error is thrown during runtime.

-   *Remove*: Invalid characters are removed.

-   *Substitute*: Invalid characters are substituted by \#.


If this configuration option is not available \(because your are using an older version, for example\), the default behavior is to throw an exception.

> ### Note:  
> A character is considered valid, if it is part of the range listed here:
> 
> -   *Character Range for XML 1.0*:
> 
>     `#x9 | #xA | #xD | [#x20-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]`*/\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
> 
>     See also: [https://www.w3.org/TR/2008/REC-xml-20081126/\#charsets](https://www.w3.org/TR/2008/REC-xml-20081126/#charsets).
> 
> -   *Character Range for XML 1.1*:
> 
>     `[#x1-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]` */\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
> 
>     See also: [https://www.w3.org/TR/2006/REC-xml11-20060816/\#charsets](https://www.w3.org/TR/2006/REC-xml11-20060816/#charsets).
> 
>     Restricted characters will be escaped automatically when *Remove* or *Substitute* is used: `[#x1-#x8] | [#xB-#xC] | [#xE-#x1F] | [#x7F-#x84] | [#x86-#x9F]`.



</td>
</tr>
</table>

Select the *Conditions* tab and provide values in the fields as follows.

**Conditions**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Maximum Message Size

</td>
<td valign="top">

This parameter allows you to configure a maximum size for inbound messages \(smallest value for a size limit is 1 MB\). All inbound messages that exceed the specified size \(per integration flow and on the runtime node where the integration flow is deployed\) are blocked.

To configure the maximum message size, you can specify the following parameters:

-   Body Size

-   Attachment Size


If a message is rejected because it exceeds the configured limit, the sender receives an error message.

</td>
</tr>
</table>

**Related Information**  


[Blog: Ensuring Exactly Once In Order Quality of Service in Cloud Integration](https://community.sap.com/t5/integration-blog-posts/ensuring-exactly-once-in-order-quality-of-service-in-cloud-integration/ba-p/14180026)

[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/24585cc503334e6c917ef383efb5558a.html "") :arrow_upper_right:

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[Setting Up Inbound HTTP Connections (Integration Flow Processing), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.") :arrow_upper_right:

[IDoc Sender Scenario](idoc-sender-scenario-7266628.md "")

