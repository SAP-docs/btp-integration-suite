<!-- loiod73227400c2b47bbbb8299740bdab41d -->

# Addressing the CISUsers Entity \(for User Creation\)

If you want to connect your Cloud Integration account to a separate Cloud Identity service, you can use the OData API to create users that a client of the Cloud Integration tenant can use to send HTTP messages via basic authentication to the runtime nodes.

The OData API allows you to create, update, read, and delete users within the Cloud Identity service that is connected to your account.



<a name="loiod73227400c2b47bbbb8299740bdab41d__section_zv2_k3h_ccb"/>

## Create User

`https://<tmn>/api/v1/CISUsers`

HTTP Method: POST

HTTP Headers:

****


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Content-Type

</td>
<td valign="top">

application/json;charset=utf-8

</td>
<td valign="top">

Content type must be JSON and the charset UTF-8.

</td>
</tr>
<tr>
<td valign="top">

Accept

</td>
<td valign="top">

application/json

</td>
<td valign="top">

If not set, the body of the HTTP response will contain XML data. If set, the response will be JSON data.

</td>
</tr>
</table>

HTTP request body \(example\):

```
{
   "Email": "xxx@sap.com"
}
```

HTTP response, when Accept "application/json" is set and creation was successful \(HTTP response code 201\):

```
{
  "d": {
    "__metadata": {
      "id": "https://<acccount>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000051')",
      "uri": "https://<account>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000051')",
      "type": "com.sap.hci.api.CISUser"
    },
    "Email": "xxx@sap.com",
    "CisId": "P000051"
  }
}
```

You have to specify the `CisId` property as well as the `Email` property because `CisId` is a key field.

**Properties in the Request Body**


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Email

</td>
<td valign="top">

Yes

</td>
<td valign="top">

E-mail address can only be used once to create a user.

</td>
</tr>
<tr>
<td valign="top">

CisId

</td>
<td valign="top">

No

</td>
<td valign="top">

CisId will contain the internal user ID after a user has been created. CisId will be ignored within an HTTP POST request body.

</td>
</tr>
<tr>
<td valign="top">

LoginName

</td>
<td valign="top">

No

</td>
<td valign="top">

Can be used to set a login name for the user.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

No

</td>
<td valign="top">

Not used yet

</td>
</tr>
<tr>
<td valign="top">

Password

</td>
<td valign="top">

No

</td>
<td valign="top">

You can use this property to set an initial password. When a password is set, the account is activated, but an e-mail is still sent to the specified e-mail address.

</td>
</tr>
<tr>
<td valign="top">

FamilyName

</td>
<td valign="top">

No

</td>
<td valign="top">

You can use this property to set the family name of the user.

</td>
</tr>
<tr>
<td valign="top">

GivenName

</td>
<td valign="top">

No

</td>
<td valign="top">

You can use this property to set the given name of the user.

</td>
</tr>
</table>

**Response Status and Error Codes**


<table>
<tr>
<th valign="top">

Response Code

</th>
<th valign="top">

Response Description

</th>
</tr>
<tr>
<td valign="top">

201 OK

</td>
<td valign="top">

User successfully created.

</td>
</tr>
<tr>
<td valign="top">

400 Bad Request

</td>
<td valign="top">

Wrong properties used.

</td>
</tr>
<tr>
<td valign="top">

401 Unauthorized

</td>
<td valign="top">

User of the call to the OData API does not exist in the Cloud Identity service or the password is wrong.

</td>
</tr>
<tr>
<td valign="top">

403 Forbidden

</td>
<td valign="top">

User not assigned the appropriate role. Assign either the `AuthGroup.TenantPartnerDirectoryConfigurator` or `AuthGroup.Administrator` authorization group or the `CloudIdentityService.Write` role.

Compare the user name in the role assignment \(case-sensitive\).

</td>
</tr>
<tr>
<td valign="top">

500 Internal Server Error

</td>
<td valign="top">

Creation of user failed. For more details, check the Java trace files. A possible reason for the error is that the e-mail address is already used.

</td>
</tr>
</table>



<a name="loiod73227400c2b47bbbb8299740bdab41d__section_etf_dkh_ccb"/>

## Read User

`https://<tmn>/api/v1/CISUsers('<CisId>')`

Example:

`https://<tmn>/api/v1/CISUsers('P000095')`

HTTP Method: GET

HTTP Headers:

****


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Accept

</td>
<td valign="top">

application/json

</td>
<td valign="top">

If not set, the body of the HTTP response will contain XML data. If set, the response will be JSON.

</td>
</tr>
</table>

HTTP response, when Accept "application/json" is set and creation was successful \(HTTP response code 200\):

```
{"d": {
   "__metadata":    {
      "id": "https://<account>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000095')",
      "uri": "https://<account>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000095')",
      "type": "com.sap.hci.api.CISUser"
   },
   "Email": "test@test.com",
   "CisId": "P000095",
   "LoginName": "franz",
   "Type": null,
   "Password": null,
   "FamilyName": "Smith",
   "GivenName": "John"
}}
```

The returned value for the `Password` property will always be null even if a password is set.

You can also specify the properties that are returned in the query part of the HTTP request URI, for example:

`https://<tmn>/api/v1/CISUsers('P000095')?$select=FamilyName,GivenName`



This request only returns the `FamilyName` and `GivenName` property:

```
{"d": {
   "__metadata":    {
      "id": "https://<account>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000095')",
      "uri": "https://<account>-tmn.hci.hana.ondemand.com:443/api/v1/CISUsers('P000095')",
      "type": "com.sap.hci.api.CISUser"
   },
   "FamilyName": "Smith",
   "GivenName": "John"
}}
```

**Response Status and Error Codes**


<table>
<tr>
<th valign="top">

Response Code

</th>
<th valign="top">

Response Description

</th>
</tr>
<tr>
<td valign="top">

200 OK

</td>
<td valign="top">

CISUser was found and successfully returned.

</td>
</tr>
<tr>
<td valign="top">

400 Bad Request

</td>
<td valign="top">

Wrong properties used.

</td>
</tr>
<tr>
<td valign="top">

401 Unauthorized

</td>
<td valign="top">

User of the call to the OData API does not exist in the Cloud Identity service or the password is wrong.

</td>
</tr>
<tr>
<td valign="top">

403 Forbidden

</td>
<td valign="top">

User not assigned the appropriate role. Assign either the `AuthGroup.TenantPartnerDirectoryConfigurator`, `AuthGroup.Administrator`, `AuthGroup.IntegrationDeveloper`, `AuthGroup.SystemDeveloper`, or `AuthGroup.ReadOnly`, authorization group or the `CloudIdentityService.Read` role.

</td>
</tr>
<tr>
<td valign="top">

404 Not Found

</td>
<td valign="top">

No CISUser was found for the specified CisId.

</td>
</tr>
<tr>
<td valign="top">

500 Internal Server Error

</td>
<td valign="top">

Read failed. For more details, check the Java trace files.

</td>
</tr>
</table>



<a name="loiod73227400c2b47bbbb8299740bdab41d__section_uvw_klh_ccb"/>

## Change User

`https://<tmn>/api/v1/CISUsers('<CisId>') )`

Example:

`https://<tmn>/api/v1/CISUsers('P000095')`

HTTP Method: PATCH

We recommend using the HTTP method PATCH:

In OData 2.0 specification, the HTTP method PATCH has merge semantics, whereas the HTTP method PUT is used for an update of all properties of an OData entity \(property values are replaced either by taking the values indicated in the request body, or reset to their default values if not mentioned in the request\). The HTTP PUT method is not supported.

Some HTTP clients do not support the PATCH method. In this case, you can try to use the`X-HTTP-Method-Override` request propertyץ

HTTP Headers:

****


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Content-Type

</td>
<td valign="top">

application/json;charset=utf-8

</td>
<td valign="top">

Content type must be JSON and the charset UTF-8.

</td>
</tr>
<tr>
<td valign="top">

Accept

</td>
<td valign="top">

application/json

</td>
<td valign="top">

If not set, the body of the HTTP response will contain XML data. If set, the response will be JSON.

</td>
</tr>
</table>

HTTP request body \(example\):

```
{"Email":"test3@test.com", "LoginName":"SmithJ", "FamilyName":"Smith", "GivenName":"John", "Password":"password1234"}

```

The properties provided in the request are merged with the existing properties. Therefore, you can only specify a subset of the properties. For example, if you only want to change the password, then you only specify the `Password` property.

HTTP request body \(example of changing the password only\):

```
{"Password":"Pass1234"}
```

Properties whose values are null in the request body are ignored during the merge.

Example:

```
{"LoginName":null}
```

If you want to initialize a property, use the empty value, for example:

```
{"LoginName":""}
```

Empty values are not possible for the properties `Email` and `Password`.

Properties in the request body:

**Properties in the Request Body**


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Email

</td>
<td valign="top">

No

</td>
<td valign="top">

E-mail address must be unique.

</td>
</tr>
<tr>
<td valign="top">

LoginName

</td>
<td valign="top">

No

</td>
<td valign="top">

Login name of the user

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

No

</td>
<td valign="top">

Not used yet

</td>
</tr>
<tr>
<td valign="top">

Password

</td>
<td valign="top">

No

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

FamilyName

</td>
<td valign="top">

No

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

GivenName

</td>
<td valign="top">

No

</td>
<td valign="top">

You can use this property to set the given name of the user.

</td>
</tr>
</table>

**Response Status and Error Codes**


<table>
<tr>
<th valign="top">

Response Code

</th>
<th valign="top">

Response Description

</th>
</tr>
<tr>
<td valign="top">

204 No Content

</td>
<td valign="top">

User was merged using the provided properties.

</td>
</tr>
<tr>
<td valign="top">

400 Bad Request

</td>
<td valign="top">

Wrong properties used.

</td>
</tr>
<tr>
<td valign="top">

401 Unauthorized

</td>
<td valign="top">

User of the call to the OData API does not exist in the Cloud Identity service or the password is wrong.

</td>
</tr>
<tr>
<td valign="top">

403 Forbidden

</td>
<td valign="top">

User not assigned the appropriate role. Assign either the `AuthGroup.TenantPartnerDirectoryConfigurator` or `AuthGroup.Administrator` authorization group or the `CloudIdentityService.Write` role.

</td>
</tr>
<tr>
<td valign="top">

500 Internal Server Error

</td>
<td valign="top">

Changing the user properties failed. For more details, check the Java trace files. Possible reasons for the error are:

The user with the specified CisId no longer exists. In this case, the response body contains a message such as `Update of the user with ID P000095 failed. HTTP response code of Identity Service is: 400 - User with [id] not found.`

The provided password is insufficient, because it does not fulfill the requirements of a valid password.

The provided `Email` value is already used with another CISUser.

</td>
</tr>
</table>



<a name="loiod73227400c2b47bbbb8299740bdab41d__section_ejy_r4h_ccb"/>

## Delete User

`https://<tmn>/api/v1/CISUsers('<CisId>') )`

Example:

`https://<tmn>/api/v1/CISUsers('P000095')`

HTTP Method: DELETE

HTTP response code for successful deletion: 200:

**Response Status and Error Codes**


<table>
<tr>
<th valign="top">

Response Code

</th>
<th valign="top">

Response Description

</th>
</tr>
<tr>
<td valign="top">

200 OK

</td>
<td valign="top">

CISUser was successfully deleted.

</td>
</tr>
<tr>
<td valign="top">

400 Bad Request

</td>
<td valign="top">

Wrong properties used.

</td>
</tr>
<tr>
<td valign="top">

401 Unauthorized

</td>
<td valign="top">

User of the call to the OData API does not exist in the Cloud Identity service or the password is wrong.

</td>
</tr>
<tr>
<td valign="top">

403 Forbidden

</td>
<td valign="top">

User not assigned the appropriate role. Assign either the `AuthGroup.TenantPartnerDirectoryConfigurator` or `AuthGroup.Administrator` authorization group or the `CloudIdentityService.Write` role.

</td>
</tr>
<tr>
<td valign="top">

500 Internal Server Error

</td>
<td valign="top">

User deletion failed. If the returned body contains a message such as `No CISUser found for CisId P000095`, deletion was not possible because a user with the specified CisId does not exist. For more details, check the Java trace files.

</td>
</tr>
</table>

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="c3f1fcd829d04a5c82a32e2fb171300c.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/d73227400c2b47bbbb8299740bdab41d.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

