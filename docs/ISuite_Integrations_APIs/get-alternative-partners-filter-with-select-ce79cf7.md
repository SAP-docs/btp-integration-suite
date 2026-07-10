<!-- loioce79cf71e4c54fddb23598eee734ea97 -->

# Get Alternative Partners \(Filter with Select\)

Get all alternative partners for a dedicated agency, schema, and Id. Furthermore, in the result set show only the `Pid` parameter.



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

`/AlternativePartners?$filter=Agency eq '{Agency}' and Scheme eq '{Scheme}' and Id eq '{Id}'&$select=Pid` 

</td>
</tr>
</table>

Assume that you like to get the `Pid` value for the Partner Directory entry associated with agency `agency1`, schema `schema1`, and Id `Id1`.

Therefore, you need to send the following GET request:

`https://<host address>/api/v1/AlternativePartners?$filter=Agency eq 'agency1' and Scheme eq 'schema1' and Id eq 'Id1'&$select=Pid`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As a response, you get a message that contains the following part:

```
<entry>
<id>https://<host address>/api/v1/AlternativePartners(Hexagency='6167656E637931',Hexscheme='736368656D6131',Hexid='496431')</id>
<title type="text">AlternativePartners</title>
<updated>2021-03-16T08:08:41.059Z</updated>
<category term="com.sap.hci.api.AlternativePartner" scheme="http://schemas.microsoft.com/ado/2007/08/dataservices/scheme"/>
<link href="AlternativePartners(Hexagency='6167656E637931',Hexscheme='736368656D6131',Hexid='496431')" rel="edit" title="AlternativePartner"/>
<content type="application/xml">
      <m:properties>
           <d:Pid>partnerX</d:Pid>
      </m:properties>
</content>
</entry>
```

Certain values \(for example, for the agency when indicated in the example request as `Hexagency`\) are also provided by the API in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my agency` is expressed by the following decimal numbers: `109 121 32 97 103 101 110 99 121` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 67 65 6E 63 79`. Note that `6D` is the hexadecimal representation of `109`, and so forth. That means that, for example, the value `my agency` is given in hexadecimal notation by `6D79206167656E6379`.

However, the properties `Hexagency`, `Hexscheme`, and `Hexid` aren't supported in the filter. If you use these properties, you get an empty result.

