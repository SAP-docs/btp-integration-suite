<!-- loio4e3c55458ee542d28408ce041ab74831 -->

# Configure the RabbitMQ Sender Adapter

The RabbitMQ sender adapter allows you to consume messages in SAP Integration Suite from queues on the RabbitMQ server. In addition, you use the adapter to send acknowledgements to the RabbitMQ server.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the RabbitMQ sender adapter, you can configure the following attributes.

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

    To use this option, you need to deploy a *User Credentials* artifact in the *Monitor* \> *Integrations* section under *Manage Security* \(*Security Material* tile\). Using the alias name for the Credential, adapter will get username and password to connect to the RabbitMQ server.




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

*Queue Name* 

</td>
<td valign="top">

Enter the name of the queue from which the messages will be consumed.

</td>
</tr>
<tr>
<td valign="top">

*Number of Concurrent Processes* 

</td>
<td valign="top">

Enter the number of processes running in parallel for each worker node.

</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Prefetched Messages* 

</td>
<td valign="top">

Enter the maximum number of messages that may be prefetched by one process.

</td>
</tr>
<tr>
<td valign="top">

*Acknowledgement Type* 

</td>
<td valign="top">

Specify the message delivery acknowledgement type. The following options are supported:

-   *Immediate \(Automatic\)*

    Sender adapter considers the message to be successfully delivered immediately after the message is consumed.

-   *After Processing \(Manual\)*

    Sender adapter decides when, and on what basis, an acknowledgement needs to be sent back to the RabbitMQ server. Positive or negative acknowledgement is sent depending on processing status of integration flow \(success or failure\).

    Protocol methods for acknowledgements: `basic.ack` and `basic.nack`

    `basic.ack` is used for positive acknowledgements

    `basic.nack` is used for negative acknowledgements

    Using negative acknowledgement type, a consumer is unable to process a delivery immediately but other consumers are able to process the message. RabbitMQ re-queues message for another consumer to receive and handle the message.




</td>
</tr>
</table>

