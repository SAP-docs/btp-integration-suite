<!-- loio9326107f768045f39d83a6347edb027a -->

# TLS/SSL Connection Information Variables

Integration Suite lets you enable one-way and two-way TLS/SSL support for virtual hosts.

When you access an API proxy through a virtual host that supports TLS/SSL, API Management captures information about the TLS connection. You can then access the TLS connection information in an API proxy through flow variables.

The kind of TLS/SSL information captured depends upon whether the virtual host is enabled for one-way or two-way TLS. For example, for one-way TLS, API Management captures information about TLS cipher or TLS protocol used in the TLS connection. For two-way TLS, API Management not only captures the same information as captured for one-way TLS, but also captures information about the client’s certificate \(cert\). For example, the subject or issuer DN of the client cert, the serial number of the client cert and the client cert in the PEM format.

The following are the list of flow variables that contain TLS connection information and are available for access in the API proxy:

> ### Note:  
> The following TLS information is captured for both one-way and two-way TLS when `<ConnectionProperties>` is set to true in the virtual host configuration file.


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

tls.cipher

</td>
<td valign="top">

The cipher used by the TLS/SSL connection.

</td>
</tr>
<tr>
<td valign="top">

tls.protocol

</td>
<td valign="top">

The protocol used by the TLS/SSL connection.

</td>
</tr>
<tr>
<td valign="top">

tls.server.name

</td>
<td valign="top">

The requested SNI server name.

</td>
</tr>
<tr>
<td valign="top">

tls.session.id

</td>
<td valign="top">

The session identifier.

This flow variable is available when you set either `<ConnectionProperties>` or `<ClientProperties>` to true.

</td>
</tr>
</table>

The following are the list of flow variables that contain TSL connection information pertaining to the client’s cert.

> ### Note:  
> The following TLS information is captured for two-way TLS when `<ClientProperties>` is set to true in the virtual host configuration file.


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

tls.client.s.dn

</td>
<td valign="top">

The subject Distinguished Name \(DN\) of the client cert. This variable enables you to capture information about the subject \(individual\) being certified, including common name \(client.cn\), organization \(client.organization\), organization unit \(client.organization.unit\), e-mail address \(client.email.address\), country/region codes \(client.country\), locality \(client.locality\) etc.

</td>
</tr>
<tr>
<td valign="top">

tls.client.i.dn

</td>
<td valign="top">

The issuer Distinguished Name \(DN\) of the client cert.

</td>
</tr>
<tr>
<td valign="top">

tls.client.raw.cert

</td>
<td valign="top">

The client cert in the PEM format.

</td>
</tr>
<tr>
<td valign="top">

tls.client.cert.serial

</td>
<td valign="top">

The serial number of the client cert.

</td>
</tr>
<tr>
<td valign="top">

tls.client.cert.fingerprint

</td>
<td valign="top">

The SHA1 fingerprint of the client cert.

</td>
</tr>
<tr>
<td valign="top">

tls.session.id

</td>
<td valign="top">

The session identifier.

This flow variable is available when you set either `<ConnectionProperties>` or `<ClientProperties>` to true.

</td>
</tr>
</table>

To configure a virtual host to capture the TLS/SSL information, you need to request the SAP Integration Suite operations team to set the following properties to true in the virtual host configuration file:


<table>
<tr>
<th valign="top">

Virtual Host Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ConnectionProperties

</td>
<td valign="top">

Set it to true to capture TLS connection information for both one-way and two-way TLS.

</td>
</tr>
<tr>
<td valign="top">

ClientProperties

</td>
<td valign="top">

Set it to true to capture additional information for two-way TLS.

</td>
</tr>
</table>

**Related Information**  


[Flow Variables](flow-variables-47f27da.md "This topic provides information about the flow variables.")

