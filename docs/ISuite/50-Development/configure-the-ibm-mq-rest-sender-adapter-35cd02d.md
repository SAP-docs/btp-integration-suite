<!-- loio35cd02d2004948fe891f77fdd6480daa -->

# Configure the IBM MQ \(REST\) Sender Adapter

IBM MQ Sender Adapter provides the ability to consume messages seamlessly from IBM MQ.



<a name="loio35cd02d2004948fe891f77fdd6480daa__fdsfkoesq30223"/>

## How the IBM MQ Sender Adapter Works

If you have configured the IBM MQ Sender Adapter, data exchange is performed as follows at runtime: IBM MQ sends the operation request to SAP Integration Suite tenant, IBM MQ Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.



<a name="loio35cd02d2004948fe891f77fdd6480daa__secction_3j4_rdc"/>

## Configure the IBM MQ Sender Adapter

Once you have created a sender channel and selected the IBM MQ Sender Adapter, you can configure its parameters as shown below:

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

*Address*

</td>
<td valign="top">

Specify the address of the IBM MQ endpoints.

Example: `https://web-{hostname}`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the type of authentication for connecting to IBM MQ:

-   *Basic*
-   *Token-Based*



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

*Proxy Type*

</td>
<td valign="top">

Select the proxy type:

-   *Internet*
-   *On-Premise*



</td>
</tr>
<tr>
<td valign="top">

*Location ID* 

</td>
<td valign="top">

Specify the location ID from the Cloud Connector.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

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

*API Version*

</td>
<td valign="top">

Select an API Version.

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

*Queue Name*

</td>
<td valign="top">

Specify the name of the queue from where the message is read.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action to be performed after processing the message in the queue:

-   *Delete Message after iFlow execution*: Deletes the message from the queue once the integration flow is executed. In case of integration flow failure, the message may either be retained \(not deleted\) or moved to the dead letter queue, removing it from the main queue for further action.
-   *Keep Message and Process Again*: Retrieves the first available message from the queue but leaves it in the queue for potential reprocessing.
-   *Read and Delete Message*: Reads and deletes the message from the queue after processing, with the maximum number of messages per node specified.



</td>
</tr>
<tr>
<td valign="top">

*Behavior on Failure*

</td>
<td valign="top">

Select the behavior in case of integration flow failure:

-   *Move to Dead Letter Queue*
-   *Do Not Delete*



</td>
</tr>
<tr>
<td valign="top">

*Max Number of Messages Per Node*

</td>
<td valign="top">

Specify the maximum number of messages to be retrieved per node.

> ### Note:  
> Acceptable value ranges from 1-5000.



</td>
</tr>
<tr>
<td valign="top">

*Max Number of Messages*

</td>
<td valign="top">

Specify the maximum number of messages to be retrieved per poll.

> ### Note:  
> Acceptable value ranges from 1-5000.



</td>
</tr>
<tr>
<td valign="top">

*Dead Letter Queue Name*

</td>
<td valign="top">

Specify the name of the Dead Letter Queue to which the message should be moved.

</td>
</tr>
<tr>
<td valign="top">

*MQ CSRF Token*

</td>
<td valign="top">

Specify the CSRF protection header. The value can be any valid string, including a blank string.

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

*Name*: Specify the custom header name to be passed in the request to IBM MQ.

*Value*: Specify the custom header value to be passed in the request to IBM MQ.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an asterisk\(\*\) to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

