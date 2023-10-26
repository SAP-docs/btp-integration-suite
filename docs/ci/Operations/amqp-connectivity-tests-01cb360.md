<!-- loio01cb360e45ea4890954d193da49aed9c -->

# AMQP Connectivity Tests

If you choose the AMQP \(Advanced Message Queuing Protocol\), the test tool checks if the connection is successful or not.

1. To perform the AMQP connectivity test, you need to specify the following settings:

**AMQP Connectivity Test Options**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Transport Protocol*

</td>
<td valign="top">

Select a transport protocol from the drop-down list. You can choose between

-   `TCP` 

    and

-   `WebSocket`

Default value is `TCP`

</td>
</tr>
<tr>
<td valign="top">

*Host* 

</td>
<td valign="top">

Enter the host of the messaging server \(mandatory\).

</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Enter the port of the messaging server \(mandatory\). Default values are:

-   `5671` for TCP

    or

-   `443` for WebSocket



</td>
</tr>
<tr>
<td valign="top">

*Path*

</td>
<td valign="top">

Additional attribute for the WebSocket protocol.

Access path of the messaging server. Default value is *empty*.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select a proxy type from the drop-down list:

-   `Internet` 

    or

-   `On-Premise`



</td>
</tr>
<tr>
<td valign="top">

*Location ID* 

</td>
<td valign="top">

Only if `On-Premise` is selected as *Proxy Type*.

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you 've defined for this instance, in the destination configuration on the cloud side

</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS*

</td>
<td valign="top">

Enable the secure connection via TLS \(Transport Layer Security\).

Default value: checkbox selected.

</td>
</tr>
<tr>
<td valign="top">

*Validate Server Certificate*

</td>
<td valign="top">

> ### Note:  
> Only applies if you've selected *Connect with TLS*.

Allows you to validate the server certificate.

When you’ve selected the *Validate Server Certificate* option \(which is the default setting\), the following checks are executed:

-   If the server certificate belongs to the server the client connects to,

-   If the certificate is signed by an instance the client trusts


If it wasn’t successful and there’s an error message, you can unselect the *Validate Server Certificate* option.

</td>
</tr>
</table>

2. Press *Send*.

If the connectivity test was successful, you get the information about the different checks. The server certificates are displayed. A download option is available allowing you to save and add them to your trust store.

