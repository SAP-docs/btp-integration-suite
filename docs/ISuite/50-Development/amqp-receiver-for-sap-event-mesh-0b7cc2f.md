<!-- loio0b7cc2fe80314823a728fa73564adfab -->

# AMQP Receiver for SAP Event Mesh

Enables SAP Integration Suite to send messages to queues or topics in SAP Event Mesh.



> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> To be able to connect to queues or topics, you have to create queues and/or topics in the message broker. This needs to be done in the message broker with the configuration tools provided by the message broker.

> ### Note:  
> Queues, topics, and messages can only be monitored using tools provided by the message broker. Those monitors are not integrated into SAP Integration Suite. In SAP Integration Suite, the integration flows using the AMQP adapter are monitored and the messages send to or consumed from the message broker.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



To connect SAP Cloud Integration to SAP Event Mesh, make sure to specify the following parameters in the described way:

When creating the channel \(see [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md)\), select adapter type *AMQP* \> *WebSocket*.



The following values are displayed in the *General* tab after a channel has been established. To change the configurations, you need to configure a new channel.

**General**


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

*Name/Adapter Type* 

</td>
<td valign="top">

AMQP

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

The protocol that the message broker supports:

*WebSocket*

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

*AMQP 1.0* 

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


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

*Host* 

</td>
<td valign="top">

Specify the hostname of the message broker.

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Specify the port of the message broker.

Enter `443`.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy that you’re using to connect to the target system.

Select *Internet* if you’re connecting directly to the message broker.

Select *On-Premise* if you’re connecting to an on-premise message broker.

For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Path* 

</td>
<td valign="top">

Specify the access path of the message broker.

Enter `/protocols/amqp10ws`.

</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS* 

</td>
<td valign="top">

Select this option to ensure that *TLS* is used for the connection.

</td>
</tr>
<tr>
<td valign="top">

*Location ID* \(only if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Select the authentication method the message broker supports. *SASL* is selected by default.

Select *OAuth2 Client Credentials*.

> ### Note:  
> Option *OAuth2 Client Credentials* is only available for WebSocket.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* \(only if *SASL* or *OAuth2 Client Credentials* is selected for *Authentication*\)

</td>
<td valign="top">

Specify the *OAuth2 Client Credentials* artifact.

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

*Destination Type* 

</td>
<td valign="top">

Specify if messages should be sent to queues or topics in the message broker.

You can select *Topic* or *Queue*.

Both options are supported by SAP Event Mesh.

</td>
</tr>
<tr>
<td valign="top">

*Destination Name* 

</td>
<td valign="top">

Enter the name of the queue or topic.

When you've selected *Queue* as *Destination Type*, specify the queue name as: `queue:<queue name>`

When you've selected *Topic* as *Destination Type*, specify the topic name as: `topic:<topic name>`

This value can be defined dynamically by using the following expressions: `${header.queueabc}` or `${property.queueabc}`.

</td>
</tr>
<tr>
<td valign="top">

*Expiration Period \(in s\)* 

</td>
<td valign="top">

Specify the Time to Live \(TTL\) for the message. If nothing is specified, the setting for the queue or topic subscription in the message broker applies.

</td>
</tr>
<tr>
<td valign="top">

*Delivery* 

</td>
<td valign="top">

Specify whether the message broker has to make sure that the message is not lost, even in case of unexpected terminations.

-   *Persistent*

-   *Non-Persistent*




</td>
</tr>
<tr>
<td valign="top">

*Message Type* 

</td>
<td valign="top">

Define the message type to be used for sending the message to the message broker. Choose between the following options:

-   *Automatic* \(recommended\): In this case, the adapter sets the message type based on the message format before the receiver channel.

-   *Binary*: In this case, the adapter converts the message into a binary message before sending.

-   *Text*: In this case, the adapter converts the message into a string before sending.


> ### Note:  
> Select *Binary* or *Text* only if your application receiving the message requires a specific message type.
> 
> Also, if you select *Binary* or *Text*, you can define the character encoding with the help of `CamelCharsetName` \(either header or property\) in the *Content Modifier*. In case you don't set the `CamelCharsetName` header or property, the transformation will use UTF-8 character encoding. See [Content Modifier Basics](content-modifier-basics-b0576a8.md) and [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md).



</td>
</tr>
<tr>
<td valign="top">

*Header Format Handling* 

</td>
<td valign="top">

There are two options for forwarding the message header name:

-   *Passtrough* \(default option\):

    Choose this option to pass the message header without transformation. For example, message-header.1 is forwarded as message-header.1.

-   *Replace*:

    Choose this option to replace dots and hyphens of a message header with \_HYPHEN\_ and \_DOT\_. For example, message-header.1 is forwarded as message\_HYPHEN\_header\_DOT\_1.




</td>
</tr>
</table>



<a name="loio0b7cc2fe80314823a728fa73564adfab__section_qgb_ccj_wsb"/>

## Further Constraints

The following constraints and limitations apply when using the AMQP adapter to connect SAP Cloud Integration to SAP Event Mesh:

-   Exclusive queues are supported.

-   Message groups aren't supported.

-   Topic subscriptions are supported, which means: You can subscribe queues to topics.


Furthermore, consider the following restrictions:

-   The maximum number of connections supported per service instance is: 50.

-   The maximum number of connections combined for all service instances and subscription \(per subaccount\) is: 1000.


As a consequence from this restriction, it's recommended that you use 1 service instance per queue.

For more information, see:

-   For more information and an example scenario using this option, see the following SAP Community blog: [https://blogs.sap.com/2019/11/20/cloud-integration-connecting-to-external-messaging-systems-using-the-amqp-adapter/](https://blogs.sap.com/2019/11/20/cloud-integration-connecting-to-external-messaging-systems-using-the-amqp-adapter/).

-   For more information on the constraints of SAP Event Mesh, see [Scope and Limitations](https://help.sap.com/viewer/bf82e6b26456494cbdd197057c09979f/Cloud/en-US/ac83090b07684f8e908df40d024f8fe5.html) \(for SAP Event Mesh\).


