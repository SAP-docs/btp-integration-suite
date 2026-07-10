<!-- loiob8bd3fb65e034b8da66239bd8630c567 -->

# Get Alternative Partner by Key Fields

Get an alternative Partner through key fields Agency, Scheme, and Id.



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

`/AlternativePartners(Hexagency='{Hexagency}',Hexscheme='{Hexscheme}',Hexid='{Hexid}')` 

</td>
</tr>
</table>

Assume that you like to get the alternative partner associated with agency `AgencyA`, schema `SchemeA`, and Id `Partner123`.

Therefore, you need to send the following GET request providing the hexadecimal values for the key parameters:

`https://<host address>/api/v1/AlternativePartners(Hexagency='4167656e637941',Hexscheme='536368656d6141',Hexid='506172746e6572313233')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As a response, you get a message that contains the following part:

```
<content type="application/xml">
  <m:properties>
            <d:Hexagency>4167656E637941</d:Hexagency>
            <d:Hexscheme>536368656D6541</d:Hexscheme>
            <d:Hexid>506172746E6572313233</d:Hexid>
            <d:Agency>AgencyA</d:Agency>
            <d:Scheme>SchemeA</d:Scheme>
            <d:Id>Partner123</d:Id>
            <d:Pid>PartnerZ</d:Pid>
            <d:LastModifiedBy><user who modified alternative partner></d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T08:25:53.556</d:LastModifiedTime>
            <d:CreatedBy><user who created alternative partner></d:CreatedBy>
            <d:CreatedTime>2020-07-01T11:57:26.096</d:CreatedTime>
  </m:properties>
</content>
```



Certain values \(for example, for the agency when indicated in the example request as `Hexagency`\) have to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my agency` is expressed by the following decimal numbers: `109 121 32 97 103 101 110 99 121` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 67 65 6E 63 79`. Note that `6D` is the hexadecimal representation of `109`, and so forth. That means that, for example, the value `my agency` is given in hexadecimal notation by `6D79206167656E6379`. Note that the hex values are built from the string values by first transforming the string value to a UTF-8-encoded byte array and then by calculating a hex string \(with uppercase letters 'A', 'B', 'C', 'D', 'E'\).

Java example for calculating hex values:

```
byte[] bytes = "testValue".getBytes(StandardCharsets.UTF_8);
String hexString = DatatypeConverter.printHexBinary(bytes);
```



However, the properties `Hexagency`, `Hexscheme`, and `Hexid` are not supported in the filter. If you use these properties, you get an empty result.

