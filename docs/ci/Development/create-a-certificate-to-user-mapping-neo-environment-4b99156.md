<!-- loio4b99156032bf4c1690a4f6885e872489 -->

# Create a Certificate-to-User Mapping, Neo Environment

Create a certificate-to-user mapping.



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

POST

</td>
<td valign="top">

`/CertificateUserMappings` 

</td>
</tr>
</table>

> ### Note:  
> Make sure that the PEM-DER string of the certificate is base64-encoded for the `Certificate` field.
> 
> Even if the ID specified in the POST request isn't correctly calculated, the POST response returns the correct ID.
> 
> The user supplied in the query part of the URI is only used for audit logging. It doesn't appear in the `CreatedBy` or `LastModifiedBy` property of the entity. The logged-in 'technical user' is used for the `CreatedBy` and `LastModifiedBy` properties. This behavior is different to the other entity types `StringParameter`, `BinaryParameter`, `AuthorizedUser`, and `AlternativePartnerId`.
> 
> You can execute the POST request with the same certificate several times. Unlike the other entity types, no duplicate key exception is raised. You can use the POST request to update the user.

You like to create a certificate-to-user mapping with a user `myuser` and a base64 encoded certificate that is represented by a string like the following one `LS0tLS1CRUdJTiBDRVJUV2T0Y2 .... AotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0t` \(shortened example string\).

Send the following POST request:

`https://<host address>/api/v1/CertificateUserMappings`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Add the following request body \(example content\):

```
{
  "User": "myuser",
  "Certificate": "LS0tLS1CRUdJTiBDRVJUV2T0Y2 .... AotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0t"
}
```

If the request was successful, you get a response that contains the following part:

```
<m:properties>
            <d:Id>abcd123...xyz</d:Id>
            <d:User>myuser</d:User>
            <d:Certificate>LS0tLS1CRUdJTiBDRVJUV2T0Y2 .... AotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0t</d:Certificate>
            <d:LastModifiedBy>your_user</d:LastModifiedBy>
            <d:LastModifiedTime>2021-02-23T08:57:25.021</d:LastModifiedTime>
            <d:CreatedBy>your_user</d:CreatedBy>
            <d:CreatedTime>2021-02-23T08:57:25.021</d:CreatedTime>
            <d:ValidUntil m:null="true"/>
</m:properties>
```

