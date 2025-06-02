<!-- loio029bc1baf60840c5be222ad597ac4b6a -->

# Configure the IBM MQ JMS Receiver Adapter

IBM MQ JMS Receiver Adapter provides the ability to publish messages seamlessly from IBM MQ using Java Message Service.



<a name="loio029bc1baf60840c5be222ad597ac4b6a__fdsfkoesq30223"/>

## How the IBM MQ JMS Receiver Adapter Works

If you have configured the IBM MQ JMS Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to IBM MQ \(this is a receiver system\), IBM MQ Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio029bc1baf60840c5be222ad597ac4b6a__secction_3j4_rdc"/>

## Configure the IBM MQ JMS Receiver Adapter

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

*Hostname*

</td>
<td valign="top">

Specify the hostname to connect to IBM MQ..

Example: `mqd-b57b.qm.eu-de.mq.appdomain.cloud`

</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Specify the port number to connect to IBM MQ.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the type of authentication for connecting to IBM MQ. Currently only *Basic* authentication is supported.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the User Credential artifact that stores the username-password pair.

</td>
</tr>
<tr>
<td valign="top">

*Queue Manager Name*

</td>
<td valign="top">

Specify the name of the queue manager to connect for messaging.

</td>
</tr>
<tr>
<td valign="top">

*Cipher Suite Name* 

</td>
<td valign="top">

Specify the Cipher Suite name.

</td>
</tr>
<tr>
<td valign="top">

*Application Name*

</td>
<td valign="top">

Specify the Application Name for the connection.

</td>
</tr>
<tr>
<td valign="top">

*Transport/Network Protocol*

</td>
<td valign="top">

Select the type of protocol for connecting to IBM MQ:

-   *TCP/IP*
-   *WebSphereMQ*



</td>
</tr>
<tr>
<td valign="top">

*Channel Name*

</td>
<td valign="top">

Specify the Channel Name in IBM MQ.

Example: `CLOUD.ADMIN.SVRCOS`

</td>
</tr>
<tr>
<td valign="top">

*Character Set ID \(CCSID\) for Non-ASCII Names*

</td>
<td valign="top">

Specify the Character Set ID\(CCSID\) for Non-ASCII Names for the JMS connection.

Example: `819`

</td>
</tr>
</table>

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

*Message Destination Type*

</td>
<td valign="top">

Select the Message Destination Type for which operation needs to be performed:

-   *Queue*
-   *Topic*



</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

</td>
<td valign="top">

Specify the name of the queue from where the message is read.

</td>
</tr>
<tr>
<td valign="top">

*Topic Name/String*

\(only available when *Message Destination Type* is set to *Topic*\)

</td>
<td valign="top">

Specify the name or string of the Topic from which the message will be read.

</td>
</tr>
<tr>
<td valign="top">

*Target Client*

</td>
<td valign="top">

Select the target client type for messages sent to IBM MQ:

-   *JMS-Compliant*: JMS message properties and headers will be accessible.
-   *WebSphereMQ \(Non-JMS\)*: JMS message properties and headers will be excluded.



</td>
</tr>
<tr>
<td valign="top">

*Transactional JMS Session*

</td>
<td valign="top">

Enable to utilize a transactional JMS session. Enabling is recommended to ensure data consistency.

</td>
</tr>
</table>

**Advanced**


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

*Message Type*

</td>
<td valign="top">

Select the Message Type:

• *Text*

• *Byte*

</td>
</tr>
<tr>
<td valign="top">

*Correlation ID*

</td>
<td valign="top">

Specify the correlation ID which is a 48 character hexadecimal encoded string, representing 24 bytes.

Example: `414d5120514d4144455620202020202067d8bf5923582e02`

> ### Note:  
> You can also specify an application-specific value like as My Custom CorelID. This sets the correlation ID of the created message.



</td>
</tr>
<tr>
<td valign="top">

*Delivery Mode*

</td>
<td valign="top">

Select the message delivery mode for the message producer:

-   *Non Persistent*
-   *Persistent*



</td>
</tr>
<tr>
<td valign="top">

*ReplyTo Destination*

</td>
<td valign="top">

Specify the destination to which the current message should be sent.

</td>
</tr>
<tr>
<td valign="top">

*Expiry*

</td>
<td valign="top">

Specify the message expiration time in milliseconds.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Priority*

</td>
<td valign="top">

Specify the priority for the message. The value can range from 0-9.

Example: `5`

</td>
</tr>
<tr>
<td valign="top">

*Time Stamp*

</td>
<td valign="top">

Specify the message timestamp in milliseconds.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*JMS Message Properties*

</td>
<td valign="top">

Specify JMS Message Properties using *Name*,*Value*, and *Data Type*.

</td>
</tr>
</table>

