<!-- loio881f65686e874cd0a72902c0a937f996 -->

# Configure the Advanced Event Mesh Receiver Adapter

The AdvancedEventMesh receiver adapter allows SAP Integration Suite to send messages to queues or topics in SAP Integration Suite, advanced event mesh.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

> ### Note:  
> -   If your current adapter version is 1.3.3 or lower, check SAP Note [3582690](https://me.sap.com/notes/3582690) before upgrading the adapter.
> -   If you run the intergration flow associated with the AEM adapter using *Run on a single worker node* configuration, there might be integration flow failures. To ensure smooth processing check SAP Note [3603502](https://me.sap.com/notes/3603502).

The adapter uses the Solace Message Format \(SMF\) message protocol.

The *General* tab displays general information about the adapter itself.

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

*Name* 

</td>
<td valign="top">

AdvancedEventMesh

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

AdvancedEventMesh

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

TCP

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

SMF

</td>
</tr>
</table>

Switch to the *Connection* tab to configure the adapter's connection details.

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

The IP address \(or host name\) to connect to. Multiple host entries separated by commas \(up to four\) are allowed for redundancy and failover. With multiple entries, each is tried in turn until one succeeds. Host contains one or more host entries \(up to four\).

A host entry has the form:

`[Protocol:]Host[:Port]`

Protocol is the protocol used for the transport channel. The valid values are:

-   `tcp` - use a TCP channel for communications between the application and its peers. If no protocol is set, tcp is used as a default.

-   `tcps` - use a SSL channel over TCP for communications between the application and its peers. The encryption with compression is not supported.


Host is the IP address \(or host name\) to connect to for a connection.

Port is the port to connect to for a connection. A value is only required when using a port other than the automatically assigned default port number. The default port for TCP is 55555 when compression is not in use, or 55003 when compression is in use. The default port for SSL is 55443.

For example, a valid entry looks like:

`tcps://192.168.1.50:55443,192.168.1.51:55443`

This specifies two hosts using SSL over TCP on port 55443.

The secured SMF host name of the event broker can be copied by navigating to the AEM service *Connect* \> *Solace Messaging* \> *Connection Details*. Copy the *Secured SMF Host* using the copy icon.

</td>
</tr>
<tr>
<td valign="top">

*Message VPN* 

</td>
<td valign="top">

Enter name of the Message VPN to attempt to join when connecting to the event broker.

</td>
</tr>
<tr>
<td valign="top">

*Username* 

</td>
<td valign="top">

The client username used for authentication with the event broker.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

The authentication mechanism to be used while connecting to advanced event mesh. The available options are:

-   *Basic*

-   *Client Certificate*

-   *OAuth2*




</td>
</tr>
<tr>
<td valign="top">

*Password Secure Alias* \(Only when using *Basic* authentication\)

</td>
<td valign="top">

The alias which defines the client password used for authentication with the event broker, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Alias* \(Only when using *Client Certificate* authentication\)

</td>
<td valign="top">

The alias of the private Key Pair in the Integration Suite's Keystore.

</td>
</tr>
<tr>
<td valign="top">

*Truststore Alias* \(Only when using *Client Certificate* authentication\)

</td>
<td valign="top">

The alias of the Certificate in the Integration Suite's Keystore. This is optional and maybe necessary only if event broker host certificate requires to be trusted or not recognized by the JRE.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Credential Type* \(Only when using *OAuth2* authentication\)

</td>
<td valign="top">

The type of OAuth2 credential type to be used. The available options are:

-   *OAuth2 Client Credentials \(Integration Suite managed OAuth2 credential store\)*

-   *OAuth2 Authorization Code \(Integration Suite managed OAuth2 credential store\)*

-   *OAuth2 - Custom \(Adapter managed OAuth2 credential store\)*




</td>
</tr>
<tr>
<td valign="top">

*Access Token Fetch/Refresh Interval \(in secs\)* \(Only when using *OAuth2* authentication\)

</td>
<td valign="top">

The interval in seconds for fetching the access token from the respective Integration Suite's credential store when OAuth2 credential type is *Client Credentials* or *Authorization Code*. When *OAuth2 - Custom* type is selected, it is the interval at which the token is refreshed. By default, the value is 300 secs.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Client Credentials Credential Name* \(Only when using *OAuth2* authentication and *OAuth2 Client Credentials* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the deployed OAuth2 Client Credentials artifact in the Integrations Suite's Credential Store. See [Deploying an OAuth2 Client Credentials](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/deploying-oauth2-client-credentials-artifact) 

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Authorization Code Credential Name*

\(Only when using *OAuth2* authentication and *OAuth2 Authorization Code* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the deployed *OAuth2 Authorization Code* artifact in the Integrations Suite's Credential Store. See [Deploying an OAuth2 Authorization Code](deploying-an-oauth2-authorization-code-081bfd7.md) 

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Access Token Secure Alias* \(Only when using *OAuth2* authentication and *OAuth2 - Custom* OAuth2 credential type\)

</td>
<td valign="top">

The alias of OAuth2 Access token, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Refresh Token Secure Alias* \(Only when using *OAuth2* authentication and *OAuth2 - Custom* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the OAuth2 Refresh token, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Client ID Secure Alias* \(Only when using *OAuth2* authentication and *OAuth2 - Custom* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the OAuth2 Client ID, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Refresh Token URL Secure Alias* \(Only when using *OAuth2* authentication and *OAuth2 - Custom* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the OAuth2 Refresh token URL, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*JCSMP Properties* 

</td>
<td valign="top">

A map of key-value pairs to configure additional connection properties. For more information, see the product documentation on Solace PubSub+ Platform.

When using the `client_name` property, the provided value is always appended with a unique 10-character alphanumeric string separated by a `/`.

For example, if the provided value is `iflow_x_sender`, the client\_name is `iflow_x_sender/az077ylyln`.

> ### Note:  
> JCSMP channel property keys must be prepended by `CLIENT_CHANNEL_PROPERTIES`.

For example:

-   `GENERATE_SENDER_ID` \(regular JCSMP property\)

-   `CLIENT_CHANNEL_PROPERTIES.ReconnectRetries` \(JCSMP channel property\)




</td>
</tr>
</table>

Switch to the *Processing* tab to configure the adapter's message processing details.

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

*Delivery Mode* 

</td>
<td valign="top">

The delivery mode for the message being published to the broker. The available options are:

-   *Direct*

-   *Persistent \(Guaranteed\)*




</td>
</tr>
<tr>
<td valign="top">

*Endpoint Type* 

</td>
<td valign="top">

The endpoint/destination type for the message being published. The available options are:

-   *Topic*

-   *Queue*




</td>
</tr>
<tr>
<td valign="top">

*Destination Name* 

</td>
<td valign="top">

The name of the endpoint/destination for the message being published. It can the name of Topic or Queue based on your selection of the *Endpoint Type*. This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`.

> ### Note:  
> When using the Receiver as a Replier in the Request-Reply pattern, to set the Destination Name dynamically use the expression \`$\{header.ReplyToDestination\}\`



</td>
</tr>
<tr>
<td valign="top">

*Message Type* 

</td>
<td valign="top">

The message type to be used for publishing the message to the broker. The available options are:

-   *Automatic \(recommended\):* The adapter sets the message type based on the message format before the Receiver.

-   *Binary:* The adapter converts the message into a Binary type before sending.

-   *Text:* The adapter converts the message into a String type before sending.

-   *Map:* The adapter converts the message into a Map type before sending.




</td>
</tr>
<tr>
<td valign="top">

*Convert Publish Into Synchronous Requestor* 

</td>
<td valign="top">

Enable if this is a Request in the Adapter Request/Reply pattern. This will send a Request to the configured Destination, set the ReplyToDestination and CorrelationId, and synchronously wait for a Reply for the duration of the *Reply Timeout\(ms\)* property.

</td>
</tr>
<tr>
<td valign="top">

*Reply Timeout \(ms\)* \(Only when *Convert Publish Into Synchronous Requestor* is selected\)

</td>
<td valign="top">

The timeout for Request-Reply Pattern.

</td>
</tr>
</table>

**Message Properties**


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

*Time To Live \(ms\)* 

</td>
<td valign="top">

The number of milliseconds before the message is discarded or moved to a Dead Message Queue. The message is set to never expire when this is left blank. Explicitly setting this to 0 resets message expiration to 0. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Is DMQ Eligible?* 

</td>
<td valign="top">

Set the message to be eligible for moving to a Dead Message Queue. Select *None* if you would like to use Exchange Header as pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Is Eliding Eligible?* 

</td>
<td valign="top">

Sets whether the message is eligible for eliding. Select *None* if you would like to use Exchange Header as pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Priority* 

</td>
<td valign="top">

The valid priority value range is 0-255 with 0 as the lowest priority and 255 as the highest. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Sender Timestamp \(ms\)* 

</td>
<td valign="top">

Allows the application to set the send timestamp overriding the API's generated value. Value is in milliseconds, from midnight, January 1, 1970 UTC. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Sequence Number* 

</td>
<td valign="top">

Sets the sequence number for the message being published. If sequence number generation is enabled, this value overrides the generated value. This field can be set automatically during message publishing, but existing values are not overwritten if set, as when a message is sent multiple times. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Application Message ID* 

</td>
<td valign="top">

Sets the application message ID \(a string for an application-specific message identifier\).This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Application Message Type* 

</td>
<td valign="top">

Sets the application message-type. <br/\><br/\>This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Sender ID* 

</td>
<td valign="top">

Sets the Sender Id for the message to be published.This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Class Of Service* 

</td>
<td valign="top">

Sets the Class of Service \(CoS\) value for message to be published. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
</table>

*Reply Message Properties*When the Receiver to publish a reply message in the Request-Reply pattern.

> ### Note:  
> These Properties are not available when *Is Requestor* is enabled as they don't apply to the Requestor in the Request-Reply pattern.

**Reply Message Properties**


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

*Is Reply?* 

</td>
<td valign="top">

Specify if this is a reply message in a Request-Reply messaging pattern, when the Receiver is used as a Replier. Select 'None' if you would like to use Exchange Header as pass-through.

</td>
</tr>
<tr>
<td valign="top">

*ReplyTo Destination Name* 

</td>
<td valign="top">

Use this to set the reply-to Destination Name on the message being published to the broker, in a Request-Reply messaging pattern. This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
<tr>
<td valign="top">

*ReplyTo Endpoint Type* 

</td>
<td valign="top">

Use this to set the reply-to Endpoint type on the message being published to the broker, in a Request-Reply messaging pattern. The available options are:

-   *Topic*

-   *Queue*


Select *None* if you would like to use Exchange Header as pass-through.

</td>
</tr>
<tr>
<td valign="top">

*Correlation ID* 

</td>
<td valign="top">

Sets the correlation ID for Request-Reply messaging. This value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`. The correlation ID is used for correlating a request to a reply. Leaving it blank will ensure the Exchange Header is pass-through.

</td>
</tr>
</table>

*Additional Properties*

*User Properties* is Map \(key-value\) type header. It allows users to specify their own user properties to be carried in the message separate from the payload.

****


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

*Key* 

</td>
<td valign="top">

The key/name of the User Property.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

The value of the respective User Property's key/name. The value can be defined dynamically by using the following expressions: \`$\{header.headerName\}\` or \`$\{property.propertyName\}\`.

</td>
</tr>
</table>

*Message Headers*

The adapter accepts headers on both sender and receiver side.

The receiver can support the following headers on the message being published to the broker: ApplicationMessageId, ApplicationMessageType, CoS, CorrelationId, DeliveryCount, Destination, DestinationEndpointType, Expiration, HttpContentEncoding, HttpContentType, IsDiscardIndication, IsDMQEligible, IsElidingEligible, IsRedelivered, IsReplyMessage, Priority, ReceiveTimestamp, ReplicationGroupMessageId, ReplyToEndpointType, ReplyToDestination, SenderId, SenderTimestamp, SequenceNumber, TimeToLive, UserProperties. When setting up the integration flow, add them to the allowlist via Integration Flow -\> Runtime Configuration -\> Allowed Header\(s\), if required. See [Specify the Runtime Configuration](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/specify-runtime-configuration). Some of these headers can be defined at design-time via the *Message Properties* tab and the rest could be defined using a Content Modifier.

Additionally, the header `SAP_MplCorrelationId` is propagated in every outgoing message as an entry in the UserProperties.

