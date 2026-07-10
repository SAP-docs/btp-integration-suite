<!-- loio7e6baf317ae64386af42d0d3b9aa6f2d -->

# Create Alternative Partner

Create an alternative partner.



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

POST

</td>
<td valign="top">

`/AlternativePartners` 

</td>
</tr>
</table>

Provide the following request body:

```
{
  "Agency": "string",
  "Scheme": "string",
  "Id": "string",
  "Pid": "string"
}
```

If you set the optional query parameter `user`, this user is used for audit logging instead of the user that is initiating the request.

Assume that you like to create a new alternative partner with the following attributes:

-   Agency: `myagency`

-   Scheme: `myschema`

-   Id: `myId`

-   Pid: `partner1234`


Therefore, you need to send the following POST request:

`https://<host address>/api/v1/AlternativePartners`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Provide the following request body:

```
{
  "Agency": "myschema",
  "Scheme": "myschema",
  "Id": "myId",
  "Pid": "partner1234"
}
```

As a response, you get a message that contains the following part:

```
<m:properties>
            <d:Hexagency>6D79736368656D61</d:Hexagency>
            <d:Hexscheme>6D79736368656D61</d:Hexscheme>
            <d:Hexid>6D794964</d:Hexid>
            <d:Agency>myschema</d:Agency>
            <d:Scheme>myschema</d:Scheme>
            <d:Id>myId</d:Id>
            <d:Pid>partner1234</d:Pid>
            <d:LastModifiedBy><user who modified alternative partner></d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T07:31:05.761</d:LastModifiedTime>
            <d:CreatedBy><user who created alternative partner></d:CreatedBy>
            <d:CreatedTime>2021-03-16T07:31:05.761</d:CreatedTime>
        </m:properties>
```

Certain values \(for example, for the agency when indicated in the example request as `Hexagency`\) are also provided by the API in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my agency` is expressed by the following decimal numbers: `109 121 32 97 103 101 110 99 121` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 67 65 6E 63 79`. Note that `6D` is the hexadecimal representation of `109`, and so forth. That means that, for example, the value `my agency` is given in hexadecimal notation by `6D79206167656E6379`.

