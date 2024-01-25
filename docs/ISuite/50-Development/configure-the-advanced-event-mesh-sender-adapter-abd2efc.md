<!-- loioabd2efcc810442edaf17a750904d1d3a -->

# Configure the Advanced Event Mesh Sender Adapter

The Advanced Event Mesh \(AEM\) sender adapter allows you to consume messages in SAP Integration Suite from queues or subscriptions on an AEM broker using the SMF message protocol.

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

The host name of the event broker.

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

*Password Secure Alias\(Only when using Basic authentication\)* 

</td>
<td valign="top">

The alias which defines the client password used for authentication with the event broker, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Alias\(Only when using Client Certificate authentication\)* 

</td>
<td valign="top">

The alias of the private Key Pair in the Integration Suite's Keystore.

</td>
</tr>
<tr>
<td valign="top">

*Truststore Alias\(Only when using Client Certificate authentication\)* 

</td>
<td valign="top">

The alias of the Certificate in the Integration Suite's Keystore. This is optional and maybe necessary only if event broker host certificate requires to be trusted or not recognized by the JRE.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Credential Type\(Only when using \`OAuth2\` authentication\)* 

</td>
<td valign="top">

The type of OAuth2 credential type to be used. The available options are:

-   OAuth2 Client Credentials \(Integration Suite managed OAuth2 credential store\)

-   OAuth2 Authorization Code \(Integration Suite managed OAuth2 credential store\)

-   OAuth2 - Custom \(Adapter managed OAuth2 credential store\)




</td>
</tr>
<tr>
<td valign="top">

*Access Token Fetch/Refresh Interval \(in secs\) \(Only when using \`OAuth2\` authentication\)* 

</td>
<td valign="top">

The interval in seconds for fetching the access token from the respective Integration Suite's credential store when OAuth2 credential type is *Client Credentials* or *Authorization Code*. When *OAuth2 - Custom* type is selected, it is the interval at which the token is refreshed. By default, the value is 300 secs.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Client Credentials Credential Name \(Only when using \`OAuth2\` authentication and \`OAuth2 Client Credentials\` OAuth2 credential type\)* 

</td>
<td valign="top">

The alias of the deployed OAuth2 Client Credentials artifact in the Integrations Suite's Credential Store. See \[Deploying an OAuth2 Client Credentials\]\(https://help.sap.com/docs/cloud-integration/sap-cloud-integration/deploying-oauth2-client-credentials-artifact\) know more.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Authorization Code Credential Name\(Only when using \`OAuth2\` authentication and \`OAuth2 Authorization Code\` OAuth2 credential type\)* 

</td>
<td valign="top">

The alias of the deployed OAuth2 Authorization Code artifact in the Integrations Suite's Credential Store. See \[Deploying an OAuth2 Authorization Code\]\(https://help.sap.com/docs/cloud-integration/sap-cloud-integration/deploying-oauth2-authorization-code\) know more.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Access Token Secure Alias\(Only when using \`OAuth2\` authentication and \`OAuth2 - Custom\` OAuth2 credential type\)* 

</td>
<td valign="top">

The alias of OAuth2 Access token, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Refresh Token Secure Alias\(Only when using \`OAuth2\` authentication and \`OAuth2 - Custom\` OAuth2 credential type\)* 

</td>
<td valign="top">

The alias of the OAuth2 Refresh token, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Client ID Secure Alias\(Only when using \`OAuth2\` authentication and \`OAuth2 - Custom\` OAuth2 credential type\)* 

</td>
<td valign="top">

The alias of the OAuth2 Client ID, stored as Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*OAUTH2 Refresh Token URL Secure Alias\(Only when using \`OAuth2\` authentication and \`OAuth2 - Custom\` OAuth2 credential type\)* 

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

A map of key-value pairs to configure additional connection properties. See `https://docs.solace.com/API-Developer-Online-Ref-Documentation/java/com/solacesystems/jcsmp/JCSMPProperties.html` and `href="https://docs.solace.com/API-Developer-Online-Ref-Documentation/java/com/solacesystems/jcsmp/JCSMPChannelProperties.html` for the available options.

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




</td>
</tr>
<tr>
<td valign="top">

*Topic Subscriptions\(Only when using \`Direct\` consumer mode\)* 

</td>
<td valign="top">

The list of AEM topic subscriptions from which messages will be consumed.

> ### Note:  
> Special characters may need to be UTF-8 encoded. For example: \`\>\` as \`%3E\`.



</td>
</tr>
<tr>
<td valign="top">

*Parallel Consumers\(Only when using \`Guaranteed\` consumer mode\)* 

</td>
<td valign="top">

The number of concurrent consumer flows.

> ### Note:  
> If the IFlow is running with more than 1 worker, this will be a multiple of the number of workers. For eg. if you configure this value to 3 and the IFlow is running with 2 workers, in total there will be 6 consumers.



</td>
</tr>
<tr>
<td valign="top">

*Selector\(Only when using \`Guaranteed\` consumer mode\)* 

</td>
<td valign="top">

A SQL-92 selector to filter messages for consumption.

</td>
</tr>
<tr>
<td valign="top">

*Acknowledgment Mode\(Only when using \`Guaranteed\` consumer mode\)* 

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

*Settlement Outcome After Maximum Attempts\(Only when using \`Guaranteed\` consumer mode and \`Automatic On Exchange Complete\` acknowledgment mode\)* 

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

</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in ms\)\(Only when using more than 1 maximum message processing attempts\)* 

</td>
<td valign="top">

The initial time interval to delay retrying to process a message.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in ms\)\(Only when using more than 1 maximum message processing attempts\)* 

</td>
<td valign="top">

The maximum time interval to delay retrying to process a message.

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff Multiplier\(Only when using more than 1 maximum message processing attempts\)* 

</td>
<td valign="top">

The multiplier to apply to the current time interval delay after every subsequent retry of a message. If set to \`1\`, this is equivalent to applying a fixed delay.

</td>
</tr>
<tr>
<td valign="top">

*Message Headers* 

</td>
<td valign="top">

The adapter accepts headers on both Sender and Receiver side.

The Sender adds the following headers: ApplicationMessageId, ApplicationMessageType, CoS, CorrelationId, DeliveryCount, Destination, DestinationEndpointType, Expiration, HttpContentEncoding, HttpContentType, IsDiscardIndication, IsDMQEligible, IsElidingEligible, IsRedelivered, IsReplyMessage, Priority, ReceiveTimestamp, ReplicationGroupMessageId, ReplyToEndpointType, ReplyToDestination, SenderId, SenderTimestamp, SequenceNumber, TimeToLive, UserProperties. When setting up the integration flow, add them to the allowlist via Integration Flow -\> Runtime Configuration -\> Allowed Header\(s\), if required. See [Specify the Runtime Configuration](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/specify-runtime-configuration)

</td>
</tr>
</table>

