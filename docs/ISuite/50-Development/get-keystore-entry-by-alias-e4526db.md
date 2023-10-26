<!-- loioe4526db64d3145099ee1f3f265009e15 -->

# Get Keystore Entry by Alias

Get a single keystore entry by alias.



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

`/KeystoreEntries('{Hexalias}')` 

</td>
</tr>
</table>

Assume that your tenant keystore contains a keystore entry with alias `smtp.mail.yahoo.com` \(server certificate for the Yahoo mail server\) and you like to export it. The hexadecimal value of the alias is: `736d74702e6d61696c2e7961686f6f2e636f6d`

Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.

Therefore, you need to send the following GET request:

`https://<host address>/api/v1/KeystoreEntries('736d74702e6d61696c2e7961686f6f2e636f6d')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As a response, you get a message for the keystore entry that contains the following part:

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

You can design an integration flow that evaluates the validity of the keystore entry and sends out a notification if the entry soon expires.

For an example scenario \(checking for the validity of certificate-to-user mappings\), check out the following SAP Community blog: [Cloud Integration – Automated Notification for Client Certificates Reaching Expiry](https://blogs.sap.com/2019/03/01/sap-cloud-platform-integration-automated-notification-for-client-certificates-reaching-expiry/).

