<!-- loio9437957aa87d4ec9a80a715d903ba5a3 -->

# Read Expiration Date of a Client Certificate, Neo Environment

Read the expiration date of a client certificate associated with a certificate-to-user mapping.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

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

`/CertificateUserMappings?$select=Id,User,ValidUntil` 



</td>
</tr>
</table>

The following example request reads the expiration date \(`ValidUntil`\) of the client certificate associated with all deployed certificate-to-user mappings \(together with Id and target user of the certificate-to-user mapping\).

`https://<host address>/api/v1/CertificateUserMappings?$select=Id,User,ValidUntil`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

If the request was successful, you get a response that contains one or multiple parts with the following attributes \(example\):

```
<m:properties>
<d:Id>abcd123...xyz</d:Id>
<d:User>myuser</d:User>
<d:ValidUntil>1747094340000</d:ValidUntil>
</m:properties>
```

Using such a request, you can design an integration flow that evaluates the expiration dates of all client certificates \(associated with certificate-to-user mappings\) and sends out a notification if the entry soon expires.

For an example scenario, check out the following SAP Community blog: [Cloud Integration – Automated Notification for Client Certificates Reaching Expiry](https://blogs.sap.com/2019/03/01/sap-cloud-platform-integration-automated-notification-for-client-certificates-reaching-expiry/).

