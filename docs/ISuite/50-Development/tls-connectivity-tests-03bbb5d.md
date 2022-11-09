<!-- loio03bbb5da16854f5aaf4ad4a26014c8a7 -->

# TLS Connectivity Tests

When you've chosen the TLS connection, the test tool checks the following:

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://launchpad.support.sap.com/#/notes/2752867).

-   if the receiver \(host\) is reachable for the tenant.
-   if the keystore is deployed correctly and contains those keys that are required for the specified authentication method during TLS handshake.

To perform the TLS connectivity test, you need to specify the following settings:

**TLS Connectivity Test Options**


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

 *Host* 



</td>
<td valign="top">

Enter the host name of the receiver.

The host name must **not** contain any path or schema, for example, ***https://***\). In particular, you must **not** enter a URL as the host name.



</td>
</tr>
<tr>
<td valign="top">

 *Port* 



</td>
<td valign="top">

Enter the port that is to be used for outbound communication.

Standard port is ***443***.



</td>
</tr>
<tr>
<td valign="top">

 *Authenticate with Client Certificate* \(optional\)



</td>
<td valign="top">

Choose this option if the client is to be authenticated against the receiver \(server\) during the TLS handshake \(a mutual authentication\).

If you select this option, you can also specify the key to be used for the test.



</td>
</tr>
<tr>
<td valign="top">

 *Alias* \(only if *Authenticate with Client Certificate* has been selected\)



</td>
<td valign="top">

Enter the alias that identifies the relevant key pair for client certificate authentication.

In case the receiver requires that during the TLS handshake also the tenant \(client\) is authenticated against the receiver \(server\), you can configure the connection test accordingly \(selecting the *Authenticate with Client Certificate* option\).

In that case, provide the *Alias* \(to indicate which key is to be used from the tenant keystore\).

For the tenant to be able to authenticate itself as the client against the receiver, a suitable key has to be available in the deployed keystore.

With the *Alias* field, you can narrow down further the check that a specific key is being used \(for example, a key that matches the configuration settings in the corresponding adapter\).



</td>
</tr>
<tr>
<td valign="top">

 *Include new SAP Key* \(only if *Authenticate with Client Certificate* has been selected\)



</td>
<td valign="top">

Selecting *Include new SAP Key* allows you to execute the connectivity test with the key pair from the keystore. You can therefore test the back end connectivity before activating the new SAP key. For further information, see: [Activating a New Key Pair Provided by SAP](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/383be7ad9c8840e38facf9323619907b.html?version=Cloud&q=new%20sap%20key).



</td>
</tr>
<tr>
<td valign="top">

 *Validate Server Certificate Required* 



</td>
<td valign="top">

Allows you to validate the server certificate.

When you've selected the *Validate Server Certificate Required* option \(which is the default setting\), the following checks are executed:

-   If the server certificate belongs to the server the client connects to.

-   If the certificate is signed by an instance the client trusts.


If it wasn't successful and there's an error message, you can unselect the *Validate Server Certificate Required* option.



</td>
</tr>
</table>

If the connectivity test was successful, you get the information about the different checks. The ***Server Certificates*** are displayed.


<table>
<tr>
<th valign="top">

*Action*



</th>
<th valign="top">

*Description*



</th>
</tr>
<tr>
<td valign="top">

 *Add to keystore* 



</td>
<td valign="top">

Select to add root certificate to key store.

> ### Note:  
> Only available if the root certificate is part of the certificate chain. If the server doesn't return the root certificate during the test call, the user needs to provide a fitting root certificate manually.

> ### Caution:  
> If you add a certificate to the keystore via *Add to keystore*, this certificate is a trusted certificate for the SAP Cloud Integration system, which means that it trusts any server certificate signed by this certificate. Make sure that you only add certificates from a trustworthy source and check the fingerprint that is shown in the ensuing dialog.



</td>
</tr>
<tr>
<td valign="top">

*Download*



</td>
<td valign="top">

Select to save the server certificate chain for offline analysis.



</td>
</tr>
</table>

