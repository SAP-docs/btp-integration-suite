<!-- loiod655ab420ae34378b839beab6edc40de -->

# Configure the IBM MQ JMS Sender Adapter

IBM MQ JMS Sender Adapter provides the ability to consume messages seamlessly from IBM MQ using Java Message Service.



<a name="loiod655ab420ae34378b839beab6edc40de__variant_xyz"/>

## How the IBM MQ JMS Sender Adapter Works

If you have configured the IBM MQ JMS Sender Adapter, data exchange is performed as follows at runtime: IBM MQ sends the operation request to SAP Integration Suite tenant, IBM MQ Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.



<a name="loiod655ab420ae34378b839beab6edc40de__secction_3j4_rdc"/>

## Configure the IBM MQ JMS Sender Adapter



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

Specify the hostname to connect to IBM MQ.

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

Specify the User Credential that stores the username-password pair.

</td>
</tr>
<tr>
<td valign="top">

*Channel Name*

</td>
<td valign="top">

Specify the Channel Name in IBM MQ.

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

Select the type of protocol for connecting to IBM MQ.

-   *TCP/IP*
-   *WebSphereMQ*



</td>
</tr>
<tr>
<td valign="top">

*Character Set ID\(CCSID\) for Non-ASCII Names*

</td>
<td valign="top">

Specify the Character Set ID\(CCSID\) for Non-ASCII Names for the JMS connection.

Example: `819`

</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specify the poll interval in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

*Message Receive Wait Time \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a message to be received from IBM MQ.

</td>
</tr>
<tr>
<td valign="top">

*Process Errors as an Event*

</td>
<td valign="top">

Enable to write error events in the exchange. If disabled, issues connecting to event streams will only be written to the logs.

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

</td>
<td valign="top">

Specify the name or string of the Topic from which the message will be read.

</td>
</tr>
<tr>
<td valign="top">

*Client ID*

\(only available when *Message Destination Type* is set to *Topic*\)

</td>
<td valign="top">

Specify the Client ID for connection.

</td>
</tr>
<tr>
<td valign="top">

*Subscription ID*

\(only available when *Message Destination Type* is set to *Topic*\)

</td>
<td valign="top">

Specify the Subscription ID for connection.

</td>
</tr>
<tr>
<td valign="top">

*Target Client*

</td>
<td valign="top">

Select the target client type for messages sent to IBM MQ:

-   *JMS-Compliant*: JMS message properties and headers are accessible.
-   *WebSphereMQ \(Non-JMS\)*: JMS message properties and headers are excluded.



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
<tr>
<td valign="top">

*Failed Transaction Handling*

\(only available when *Transactional JMS Session* is enabled.\)

</td>
<td valign="top">

Select the operation when transaction fails:

-   *Keep Message and Process Again*
-   *Move Message to Another Queue*



</td>
</tr>
<tr>
<td valign="top">

*Max Delivery Count*

\(only available when *Failed Transaction Handling* is set to *Move Message to Another Queue*.\)

</td>
<td valign="top">

Specify the count for maximum attempts for JMS Message delivery.

> ### Note:  
> This value refers to JMS header JMSXDeliveryCount. Message excess of this value is moved to the Another Queue.



</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

\(only available when *Failed Transaction Handling* is set to *Move Message to Another Queue*.\)

</td>
<td valign="top">

Specify the name of the Another Queue to which the message should be moved.

</td>
</tr>
<tr>
<td valign="top">

*Poll On One Worker Only*

\(only available when *Message Destination Type* is set to *Queue*.\)

</td>
<td valign="top">

Enable to poll on a single worker node.

</td>
</tr>
<tr>
<td valign="top">

*Max Messages Per Node*

\(only available when *Message Destination Type* is set to *Queue*.\)

</td>
<td valign="top">

Specify the maximum number of messages to be retrieved per node.

> ### Note:  
> The possible values range from 1 to 5000.



</td>
</tr>
<tr>
<td valign="top">

*Max Number of Messages*

\(only available when *Message Destination Type* is set to *Topic*.\)

</td>
<td valign="top">

Specify the maximum number of messages to be retrieved.

> ### Note:  
> The possible values range from 1 to 5000.



</td>
</tr>
<tr>
<td valign="top">

*Message Selector*

</td>
<td valign="top">

Specify the value for the properties to be selected. Example: `Department=HR`.

</td>
</tr>
</table>

