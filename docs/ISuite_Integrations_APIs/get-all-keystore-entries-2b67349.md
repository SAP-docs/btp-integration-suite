<!-- loio2b67349d7f504c3dbbb88b5c375ff6ae -->

# Get All Keystore Entries

Get all entries of the tenant keystore.



Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`/KeystoreEntries` 

</td>
</tr>
</table>

Assume that your tenant keystore contains a keystore entry with alias `smtp.mail.yahoo.com` \(server certificate for the Yahoo mail server\).

Send the following GET request:

`https://<host address>/api/v1/KeystoreEntries`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As a response, you get a message that contains for each keystore entry a passage with the following structure \(assuming that your tenant keystore contains a keystore entry with alias `smtp.mail.yahoo.com`\):

```
<m:properties>
            <d:Hexalias>736D74702E6D61696C2E7961686F6F2E636F6D</d:Hexalias>
            <d:Alias>smtp.mail.yahoo.com</d:Alias>
            <d:KeyType>RSA</d:KeyType>
            <d:KeySize>2048</d:KeySize>
            <d:ValidNotBefore>2019-10-04T00:00:00Z</d:ValidNotBefore>
            <d:ValidNotAfter>2020-04-01T12:00:00Z</d:ValidNotAfter>
            ....
</m:properties>

```

You can design an integration flow that evaluates the validity of each keystore entry and sends out a notification if the validity of certain entries soon expires.

For an example scenario \(checking for the validity of certificate-to-user mappings\), check out the following SAP Community blog: [Cloud Integration – Automated Notification for Client Certificates Reaching Expiry](https://blogs.sap.com/2019/03/01/sap-cloud-platform-integration-automated-notification-for-client-certificates-reaching-expiry/).

