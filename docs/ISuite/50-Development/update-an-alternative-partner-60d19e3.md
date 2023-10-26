<!-- loio60d19e38267c4991a2f696f1a00f4ead -->

# Update an Alternative Partner

Update an alternative Partner.



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

`/AlternativePartners(Hexagency='{Hexagency}',Hexscheme='{Hexscheme}',Hexid='{Hexid}')` 

</td>
</tr>
</table>

Provide the following request body \(with the new `Pid` value\).

```
{
  "Pid": "string"
}
```

If you set the optional query parameter `user`, this user is used for audit logging instead of the user that is initiating the request.

Assume that you like to update a new alternative partner with the following attributes:

-   Agency: `AgencyA`

-   Scheme: `SchemaA`

-   Id: `Partner123`

-   New Pid: `PartnerZ`


Therefore, you need to send the following PUT request, providing the hexadecimal values for the key parameters:

`https://<host address>/api/v1/AlternativePartners(Hexagency='4167656e637941',Hexscheme='536368656d6541',Hexid='506172746e6572313233')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Provide the following request body:

```
{
  "Pid": "PartnerZ"
}
```



Certain values \(for example, for the agency when indicated in the example request as `Hexagency`\) have to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my agency` is expressed by the following decimal numbers: `109 121 32 97 103 101 110 99 121` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 67 65 6E 63 79`. Note that `6D` is the hexadecimal representation of `109`, and so forth. That means that, for example, the value `my agency` is given in hexadecimal notation by `6D79206167656E6379`. Note that the hex values are built from the string values by first transforming the string value to a UTF-8-encoded byte array and then by calculating a hex string \(with uppercase letters 'A', 'B', 'C', 'D', 'E'\).

Java example for calculating hex values:

```
byte[] bytes = "testValue".getBytes(StandardCharsets.UTF_8);
String hexString = DatatypeConverter.printHexBinary(bytes);
```

