<!-- loio1f7676849a564961872cc45999608a7e -->

# Security Elements \(Transport-Level Security\)

Each transport-level security option requires a specific set of security elements.

The following tables provide a summary of how the required security elements \(in **bold letters**\) have to be distributed among the involved components \(tenant and sender/receiver systems\).

**Transport-Level Security**


<table>
<tr>
<th valign="top">

Security Option

</th>
<th valign="top">

Direction

</th>
<th valign="top">

Required by tenant administrator …

</th>
<th valign="top">

… to do the following

</th>
<th valign="top">

Required by sender/receiver administrator …

</th>
<th valign="top">

… to do the following

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

HTTPS – basic authentication

</td>
<td valign="top" rowspan="2">

Inbound \(sender calls tenant\)

</td>
<td valign="top">

**User name** \(to be provided by sender administrator\).

This is the user under which the customer system is to call SAP Cloud Integration.

</td>
<td valign="top">

Grant the required authorizations to enable this user to call the tenant.

</td>
<td valign="top">

**Load balancer root certificate** \(to be provided by tenant administrator\)

Is required for the SSL communication step \(can be obtained via the URL of the runtime node provided in the tenant mail by SAP\).

</td>
<td valign="top">

Import into the keystore of the sender system.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

**User name and password** \(to be provided by tenant administrator\)

</td>
<td valign="top">

Enable the sender to support basic authentication.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Outbound \(tenant calls receiver\)

</td>
<td valign="top">

**Receiver server root certificate** \(to be provided by receiver administrator\)

Is required to enable HTTPS communication with the receiver system \(server\).

</td>
<td valign="top">

Import into the tenant keystore \(and deploy the keystore on the tenant\).

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

**User credentials** \(to be provided by receiver administrator\)

These are the user credentials under which the tenant is to call the receiver system.

</td>
<td valign="top">

Define the User Credentials artifact \(to be deployed on the tenant\).

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

HTTPS – certificate-based

</td>
<td valign="top" rowspan="3">

Inbound \(sender calls tenant\)

</td>
<td valign="top">

**Sender client root certificate** \(to be provided by sender administrator\)

</td>
<td valign="top">

Check whether the CA the customer system used to get its client certificate signed is already part of the load balancer \(server\) keystore.

</td>
<td valign="top">

**Load balancer server root certificate** \(to be provided by tenant administrator\)

</td>
<td valign="top">

Import into client PSE of the sender system.

</td>
</tr>
<tr>
<td valign="top">

**Sender client certificate** \(to be provided by sender administrator\)

</td>
<td valign="top">

Configure the authorization check in the integration flow.

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

**List of trusted root certificates supported by load balancer** \(to be provided by tenant administrator\)

</td>
<td valign="top">

Select a certification authority from the list for the certificate signing request for the client certificate.

</td>
</tr>
<tr>
<td valign="top">

Outbound \(tenant calls receiver\)

</td>
<td valign="top">

**Receiver server root certificate** \(to be provided by receiver administrator\)

</td>
<td valign="top">

Import into tenant keystore \(if not already there\).

</td>
<td valign="top">

**Tenant client root certificate** \(to be provided by tenant administrator\)

</td>
<td valign="top">

Import into the server PSE of the receiver system.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

Tenant client certificate \(to be provided by tenant administrator\)

</td>
<td valign="top">

Define the client certificate-to-user mapping for the configuration of authorization checks.

</td>
</tr>
<tr>
<td valign="top">

SFTP

</td>
<td valign="top">

Outbound \(tenant as SFTP client sends a request to an SFTP server\)

</td>
<td valign="top">

**SFTP server \(receiver\) public key** \(to be provided by SFTP server \(receiver\) administrator\)

Is required by tenant to check whether SFTP server can be trusted.

</td>
<td valign="top">

Add to known\_hosts file \(to be deployed as Known Hosts artifact on tenant\).

</td>
<td valign="top">

**Tenant public key** \(to be provided by tenant administrator\)

Is used to authenticate tenant as a trusted SFTP client on the SFTP server side.

</td>
<td valign="top">

Add to authorized\_keys file on the SFTP server side.

</td>
</tr>
</table>

