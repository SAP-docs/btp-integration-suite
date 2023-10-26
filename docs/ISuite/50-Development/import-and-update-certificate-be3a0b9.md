<!-- loiobe3a0b92a4a446a3ac8637e25210241f -->

# Import and Update Certificate

Import and update a certificate.



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

PUT

</td>
<td valign="top">

`/CertificateResources('{Hexalias}')/$value` 

</td>
</tr>
</table>

> ### Caution:  
> Although an HTTP PUT method is used, a new OData entity is created with the sample request.

You like to import a certificate to the tenant keystore \(with an alias `mycertificate`\). The hexadecimal value of the alias is `6d796365727469666963617465`.

Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.

Send the following PUT request:

`https://<host address>/api/v1/CertificateResources('6d796365727469666963617465')/$value`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Add the certificate content with the request body \(example content\):

```
[-----BEGIN CERTIFICATE-----
MIIDdzCCAl+gAwIBA....
....
....
R9I4LtD+gdwyah617jzV/OeBHRnDJELqYzmp
-----END CERTIFICATE-----]
```

