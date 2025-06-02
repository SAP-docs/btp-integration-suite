<!-- loioabd2efcc810442edaf17a750904d1d3a -->

# Configure the Advanced Event Mesh Sender Adapter

The AdvancedEventMesh sender adapter allows SAP Integration Suite to consume messages from queues or subscriptions in SAP Integration Suite, advanced event mesh.

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
> -   If you run the intergration flow associated with the AEM adapter using *Run on a single worker node* configuration, any lifecycle change to the node, such as software updates, out-of-memory exceptions, etc. may cause a brief delay in message consumption due to the switchover to a new node. To ensure smooth processing check SAP Note [3603502](https://me.sap.com/notes/3603502). We recommended upgrading to v1.3.5 for the fix.

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

The name of the Message VPN to attempt to join when connecting to the event broker.

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

The authentication mechanism to be used while connecting to AEM. The available options are:

-   Basic

-   Client Certificate

-   OAuth2




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

The alias of the private Key Pair in SAP Integration Suite's Keystore.

</td>
</tr>
<tr>
<td valign="top">

*Truststore Alias* \(Only when using *Client Certificate* authentication\)

</td>
<td valign="top">

The alias of the Certificate in SAP Integration Suite's Keystore. This is optional and maybe necessary only if event broker host certificate requires to be trusted or not recognized by the JRE.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Credential Type* \(Only when using *OAuth2* authentication\)

</td>
<td valign="top">

The type of OAuth2 credential type to be used. The available options are:

-   OAuth2 Client Credentials \(SAP Integration Suite managed OAuth2 credential store\)

-   OAuth2 Authorization Code \(SAP Integration Suite managed OAuth2 credential store\)

-   OAuth2 - Custom \(Adapter managed OAuth2 credential store\)




</td>
</tr>
<tr>
<td valign="top">

*Access Token Fetch/Refresh Interval \(in secs\)* \(Only when using *OAuth2* authentication\)

</td>
<td valign="top">

The interval in seconds for fetching the access token from the respective SAP Integration Suitee's credential store when OAuth2 credential type is *Client Credentials* or *Authorization Code*. When *OAuth2 - Custom* type is selected, it is the interval at which the token is refreshed. By default, the value is 300 secs.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Client Credentials Credential Name* \(Only when using *OAuth2* authentication and *OAuth2 Client Credentials* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the deployed OAuth2 Client Credentials artifact in SAP Integration Suite's Credential Store. See \[Deploying an OAuth2 Client Credentials\]\(https://help.sap.com/docs/cloud-integration/sap-cloud-integration/deploying-oauth2-client-credentials-artifact\) know more.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Authorization Code Credential Name* \(Only when using *OAuth2* authentication and *OAuth2 Authorization Code* OAuth2 credential type\)

</td>
<td valign="top">

The alias of the deployed OAuth2 Authorization Code artifact inSAP Integration Suite's Credential Store. See \[Deploying an OAuth2 Authorization Code\]\(https://help.sap.com/docs/cloud-integration/sap-cloud-integration/deploying-oauth2-authorization-code\) know more.

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
> JCSMP channel property keys must be prepended by \`CLIENT\_CHANNEL\_PROPERTIES.\`. For example:
> 
> -   \`GENERATE\_SENDER\_ID\` \(regular JCSMP property\)
> 
> -   \`CLIENT\_CHANNEL\_PROPERTIES.ReconnectRetries\` \(JCSMP channel property\)



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

*Consumer Mode* 

</td>
<td valign="top">

The adapter's consumer mode. The available options are:

-   Direct

-   Guaranteed

-   Durable Topic Endpoint




</td>
</tr>
<tr>
<td valign="top">

*Run on a single worker node?* 

</td>
<td valign="top">

When enabled, the consumer is bound to only one of the available worker nodes. It is recommended in the following cases:

-   When consuming in *Direct* mode to avoid the processing of the same message on all the worker nodes due to fanout.

-   To successfully bind to an Exclusive access type *Durable Topic Endpoint*, as it only allows one consumer binding.




</td>
</tr>
<tr>
<td valign="top">

*Topic Subscriptions* \(Only when using *Direct* consumer mode\)

</td>
<td valign="top">

The list of AEM topic subscriptions from which messages will be consumed.

> ### Note:  
> Special characters may need to be UTF-8 encoded. For example: \`\>\` as \`%3E\`.



</td>
</tr>
<tr>
<td valign="top">

*Parallel Consumers* \(Only when using *Guaranteed* or *Durable Topic Endpoint* consumer mode\)

</td>
<td valign="top">

The number of concurrent consumer flows.

> ### Note:  
> If the integration flow is processed with more than 1 worker, this will be a multiple of the number of workers. For example, if you configure this value to 3 and the integration flow is running with 2 workers, in total there will be 6 consumers.



</td>
</tr>
<tr>
<td valign="top">

*Queue Name* \(Only when using *Guaranteed* consumer mode\)

</td>
<td valign="top">

The Advanced Event Mesh queue name from which messages are consumed.

</td>
</tr>
<tr>
<td valign="top">

*Topic Endpoint Name* \(Only when using *Durable Topic Endpoint* consumer mode\)

</td>
<td valign="top">

A durable topic endpoint has an access type that determines how messages are delivered when multiple consumer flows are bound to it. Topic endpoints can be assigned one of the following access types:

-   Exclusive

    Specifies that only one client can bind to and be serviced by the topic endpoint. If other consumers attempt to bind, they are rejected.

-   Non-exclusive

    Specifies that all bound flows are able to receive messages, and when multiple flows are bound to a non-exclusive topic endpoint, they receive messages in a round-robin fashion.




</td>
</tr>
<tr>
<td valign="top">

*Topic Name* \(Only when using *Durable Topic Endpoint* consumer mode\)

</td>
<td valign="top">

The Advanced Event Mesh topic name on which the durable topic subscription needs to be made.

> ### Caution:  
> Durable Topic endpoints support a single subscription. If the topic subscription changes, all messages persisted to the topic endpoint are deleted.



</td>
</tr>
<tr>
<td valign="top">

*Selector* \(Only when using *Guaranteed* or *Durable Topic Endpoint* consumer mode\)

</td>
<td valign="top">

An SQL-92 selector to filter messages for consumption. It is a string up to a maximum of 2,000 bytes that uses a conditional expression syntax that is a subset of SQL92.

> ### Caution:  
> When binding to a topic in Durable Topic Endpoint mode: If the selector changes, all messages persisted to the topic endpoint are deleted



</td>
</tr>
<tr>
<td valign="top">

*Acknowledgment Mode* \(Only when using *Guaranteed* or *Durable Topic Endpoint* consumer mode\)

</td>
<td valign="top">

The strategy to be used when acknowledging messages. The possible options are:

-   Automatic Immediate

-   Messages are acknowledged immediately after being read from the event broker.

-   Automatic On Exchange Complete.

-   Messages are acknowledged upon exchange completion.




</td>
</tr>
<tr>
<td valign="top">

*Settlement Outcome After Maximum Attempts* \(Only when using *Guaranteed* or *Durable Topic Endpoint* consumer mode and *Automatic On Exchange Complete* acknowledgment mode\)

</td>
<td valign="top">

Settlement outcome for failed messages after all processing attempts have been exhausted. The possible options are:

-   Failed: This negative acknowledgment notifies the event broker that the message was not processed. The event broker will attempt to redeliver the message while adhering to delivery count limits.

-   Rejected: This negative acknowledgment notifies the event broker that the message was not accepted. The event broker will remove the message from its queue and then move the message to the Dead Message Queue \(DMQ\) if it is configured.




</td>
</tr>
<tr>
<td valign="top">

*Maximum Message Processing Attempts* 

</td>
<td valign="top">

The maximum number of attempts to process a message.

> ### Note:  
> This is an adapter level retry and hence will not result in DeliveryCount header increment. DeliveryCount increments only when the message is re-delivered by the event broker.



</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in ms\)* \(Only when using more than 1 maximum message processing attempts\)

</td>
<td valign="top">

The initial time interval to delay retrying to process a message.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in ms\)* \(Only when using more than 1 maximum message processing attempts\)

</td>
<td valign="top">

The maximum time interval to delay retrying to process a message.

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff Multiplier* \(Only when using more than 1 maximum message processing attempts\)

</td>
<td valign="top">

The multiplier to apply to the current time interval delay after every subsequent retry of a message. If set to \`1\`, this is equivalent to applying a fixed delay.

</td>
</tr>
</table>



<a name="loioabd2efcc810442edaf17a750904d1d3a__section_cy1_jmv_hbc"/>

## Message Headers

The adapter accepts headers on both sender and receiver side.

The sender adds the following SMF headers to the Exchange: ApplicationMessageId, ApplicationMessageType, CoS, CorrelationId, DeliveryCount, Destination, DestinationEndpointType, Expiration, HttpContentEncoding, HttpContentType, IsDiscardIndication, IsDMQEligible, IsElidingEligible, IsRedelivered, IsReplyMessage, Priority, ReceiveTimestamp, ReplicationGroupMessageId, ReplyToEndpointType, ReplyToDestination, SenderId, SenderTimestamp, SequenceNumber, TimeToLive, UserProperties.

In addition to the SMF headers there are some non-SMF headers as well that are added to the Exchange by the sender.

> ### Note:  
> These non-SMF headers are not automatically persisted on the message beyond the Exchange.

1.  LocalProcessingAttempt: The count of processing attempts per delivery of a message from the advanced event mesh Queue or Durable Topic Endpoint.

2.  TotalLocalProcessingAttempt: The total processing attempts for all deliveries which includes redelivery of a message from the advanced event mesh. Note: For the count to be accurate, ensure the DeliveryCount feature is enabled on the respective Queue or Durable Topic Endpoint and all the delivery attempts are made within the same integration flow.

3.  The sender supports the propagation of header `SAP_MplCorrelationId`. If the incoming message already contains a header `SAP_MplCorrelationId`, the same value is propagated into the exchange headers.


When setting up the integration flow, add them to the allowlist. To do that, click the modeling area outside any integration flow shape. Then, choose *Runtime Configuration* \> *Allowed Header\(s\)*, if required.

See [Specify the Runtime Configuration](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/specify-runtime-configuration)

