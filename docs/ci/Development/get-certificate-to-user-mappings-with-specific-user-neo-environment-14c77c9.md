<!-- loio14c77c949b2f4e658bb9faea237d2a9e -->

# Get Certificate-to-User Mappings with Specific User, Neo Environment

Get certificate-to-user mappings with a specific user.



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

`/CertificateUserMappings` 



</td>
</tr>
</table>



### Request Example

You like to get all certificate-to-user mappings with user `myUser`.

Send the following GET request:

`https://<host address>/api/v1/CertificateUserMappings?$filter=User eq 'myUser'`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

If the request was successful, you get a response that contains one or multiple parts with the following attributes \(example\):

```
<m:properties>
                <d:Id>abcd123...xyz</d:Id>
                <d:User>myuser</d:User>
                <d:Certificate>LS0tLS1CRUdJTiBDRVJUV2T0Y2 .... AotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0t</d:Certificate>
                <d:LastModifiedBy>your_user</d:LastModifiedBy>
                <d:LastModifiedTime>2021-02-23T08:57:25.021</d:LastModifiedTime>
                <d:CreatedBy>your_user</d:CreatedBy>
                <d:CreatedTime>2021-02-23T08:57:25.021</d:CreatedTime>
                <d:ValidUntil>1747094340000</d:ValidUntil>
</m:properties>
```

