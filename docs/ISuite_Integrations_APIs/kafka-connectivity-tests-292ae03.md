<!-- loio292ae03c88ff4718ba7be67ed66f3729 -->

# Kafka Connectivity Tests

If you choose the Kafka Connectivity test, the test tool checks if the connection is successful or not.

To perform the Kafka connectivity test, you need to specify the following settings:

**Kafka Connectivity Options**


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

Enter the host name of the messaging server.

</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Enter the port name of the messaging server.

</td>
</tr>
<tr>
<td valign="top">

*Time out \(in ms\)*

</td>
<td valign="top">

Specify the maximum amount of time the client waits for a response from the kafka broker.

Default value is: `10000 ms`

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Select the type of authentication for connecting to the broker. SASL is selected by default.

-   *SASL*

-   *Client Certificate* \(security protocol: SSL\)

-   *Connect with TLS*



</td>
</tr>
<tr>
<td valign="top">

*SASL Mechanism*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Select the SASL mechanism:

-   *PLAIN*

-   *SCRAM-SHA-256*



</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Select this option to switch between *PLAIN* and *SCRAM-SHA-256*.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the user credential on the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Client Certificate* is selected for *Authentication*\)

</td>
<td valign="top">

Enter the private key alias.

</td>
</tr>
</table>

2. Press *Send*.

If the connectivity test was successful, you get the information about existing topics in the broker. This list is limited to up to 200 topics. If there are more than 200 topics, only the first 200 are returned.

For more information about the Kafka sender adapter see: [Configure the Kafka Sender Adapter](configure-the-kafka-sender-adapter-0d849e5.md)

