<!-- loio1133cca9e3404d65bb5b6414e388a33b -->

# Export Certificate

Export a certificate from the keystore.



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

`​/KeystoreEntries('{Hexalias}')/Certificate/$value` 

</td>
</tr>
</table>

Assume that your tenant keystore contains a certificate with alias `smtp.mail.yahoo.com` \(server certificate for the Yahoo mail server\) and you like to export it. The hexadecimal value of the alias is: `736d74702e6d61696c2e7961686f6f2e636f6d`.

Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.

Therefore, you need to send the following GET request:

`https://<host address>/api/v1/KeystoreEntries('736d74702e6d61696c2e7961686f6f2e636f6d')/Certificate/$value`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As a result, you get the certificate in the following form \(content type: application/pkix-cert\):

```
-----BEGIN CERTIFICATE-----
MIIITDCCBzSgAwIBAgIQDBxHETUvPf18xKE7JdDoNjANBgkqhkiG9w0BAQsFADBw
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3
d3cuZGlnaWNlcnQuY29tMS8wLQYDVQQDEyZEaWdpQ2VydCBTSEEyIEhpZ2ggQXNz

...

F8jCgaR+bTz+hYoLtFN9mow1kr5jNgcn68HALdKF8SluCyZS5jFbDOM4HQay16pU
J++y5pvlBMtzQ571O7itrSQ32praT6whMlCBy9pAnJIKzVM4IDM5H1drHc6shhuo
+XiClYEJRHstbLVQYFwB2w==
-----END CERTIFICATE-----
```

