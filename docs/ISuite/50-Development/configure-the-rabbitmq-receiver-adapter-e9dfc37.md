<!-- loioe9dfc37fb5b349d5ad1d6e43e194e69e -->

# Configure the RabbitMQ Receiver Adapter

You use the RabbitMQ receiver adapter to send messages from SAP Integration Suite to exchanges or queues on the RabbitMQ server.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the RabbitMQ receiver adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

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

Enter the name of the channel.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

RabbitMQ

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

AMQP 0-9-1

</td>
</tr>
</table>

You can provide more information in the *Description* field.

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

Enter the host name or IP address of the RabbitMQ server.

> ### Note:  
> If unable to establish a connection with the host, configure the IP address.



</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port of the RabbitMQ server.

</td>
</tr>
<tr>
<td valign="top">

*Virtual Host* 

</td>
<td valign="top">

Enter the virtual host of the RabbitMQ server. The default virtual host is:

`/`

> ### Note:  
> If unable to establish the connection with virtual host, verify user or queue mapping for virtual host on RabbitMQ server.
> 
> Configure a guest user for the required virtual host on the RabbitMQ server for certificate-based connections.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Select the Proxy Type to connect to the target system.

-   *Internet \(On Cloud\)*

    Connects to the system through the Internet.

-   *On-Premise*

    Connects to the system Through Cloud Connector.




</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(Only if for *Proxy Type* the option *On-Premise* is selected\)

</td>
<td valign="top">

To connect to a Cloud Connector instance associated with your account, enter the location ID that you define for this instance in the destination configuration of SAP BTP cockpit.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Select authentication option to use to connect to the RabbitMQ server. There are the following options:

-   *Client Certificate*

    Connect to the RabbitMQ server using client certificate authentication.

    To use this option, you need to upload a certificate has to the keystore in the *Monitor* \> *Integrations* section under *Manage Security* \(*Keystore* tile\). Using the deployed private key, the adapter connects to the RabbitMQ server.

-   *SASL*

    Connect to the RabbitMQ server using Simple Authentication and Security Layer \(SASL\).

    To use this option, you need to deploy a *User Credentials* artifact in the *Monitor* \> *Integrations*section under *Manage Security* \(*Security Material* tile\). Using the alias name for the Credential, adapter will get username and password to connect to the RabbitMQ server.




</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(Only if for *Authentication* the option *Client Certificate* is selected\)

</td>
<td valign="top">

Alias to identify the private key in the key store to communicate with the RabbitMQ server.

</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS*

\(Only if for *Authentication* the option *SASL* is selected\)

</td>
<td valign="top">

Select to securely connect using TLS \(Security protocol: SASL\_SSL or SASL\_PLAIN\).

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(Only if for *Authentication* the option *SASL* is selected\)

</td>
<td valign="top">

Enter the alias name of the deployed *User Credentials* artifact.

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

Receiver adapter supports publishing a message to RabbitMQ server using the following types:

-   *Exchange*

-   *Queue*


The time when the message was published is captured using property `SAP_RabbitMQ_Outbound_Timestamp`.

</td>
</tr>
<tr>
<td valign="top">

*Exchange Name* 

\(Only if for *Destination Type* the option *Exchange* is selected\)

</td>
<td valign="top">

Enter the name of the exchange to which the messages is published.

</td>
</tr>
<tr>
<td valign="top">

*Routing Key* 

\(Only if for *Destination Type* the option *Exchange* is selected\)

</td>
<td valign="top">

Enter the routing key to bind or route your message.

</td>
</tr>
<tr>
<td valign="top">

*Queue Name* 

</td>
<td valign="top">

Enter the name of the queue to which the messages are published.

</td>
</tr>
<tr>
<td valign="top">

*Message Expiration Period \(TTL in ms\)* 

</td>
<td valign="top">

Enter the time period \(in milliseconds\). The messages is not stored after this time exceeds.

If you enter `0` or leave the field empty, the message does not expire.

TTL should be in millisecond \(example: `50000 m/s`\).

If the TTL value is `0` or left empty, the message doesn't expire.

</td>
</tr>
<tr>
<td valign="top">

*Message Delivery Mode* 

</td>
<td valign="top">

Specify whether the RabbitMQ server has to make sure that the message is not lost, even in case of unexpected terminations.

Specify the durability of the message. Durable or persistent message must not be lost even if RabbitMQ is unexpectedly terminated and restarted.

There are three options: persistent, non-persistent and dynamic.

Name of property: `SAP_RabbitMQ_Outbound_Message_DeliveryMode`

</td>
</tr>
<tr>
<td valign="top">

*Generate Message ID* 

</td>
<td valign="top">

This is an optional field. Enable only if you want to generate an arbitrary message ID that would be added to the property in the message exchange. This ID is useful when you are developing integration scenarios with applications that specifically look for a message ID during interactions.

</td>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Select a request parameter.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Specify the value of the property. You can also enter`${header.headername}` or `${property.propertyname}`to dynamically read the value from a header or property.

For the key `sap_rabbitmq_exchange_type`, the value will be the type of exchange supported by RabbitMQ, for example, `header`.

Maximum priority value supply from additional argument section as key and value pair.

Key : priority

Value : 1 or 2

The implementation supports a limited number of priorities: `255`. Values between `1` and `10` are recommended.

</td>
</tr>
</table>

