<!-- loio47b69992cd944e93903d46d700ec682f -->

# Requests for String Parameter, Binary Parameter, and Authorized User



<a name="loio47b69992cd944e93903d46d700ec682f__section_o5q_3r1_z4b"/>

## Create Authorized User


<table>
<tr>
<th valign="top">

Purpose

</th>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

Create authorized user.

</td>
<td valign="top">

POST

</td>
<td valign="top">

`/AuthorizedUsers` 

</td>
</tr>
</table>

Assume that you like to create an authorized user `MyUser` that is to be associated to partner with Pid `PartnerZ`.

Perform a POST request to the following address:

`https://<host address>/api/v1/AuthorizedUsers`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Provide the following request body:

```
{
  "User": "MyUser",
  "Pid": "PartnerZ"
}
```

As a response, you get a message that contains the following part:

```
<content type="application/xml">
   <m:properties>
            <d:User>myuser</d:User>
            <d:Pid>PartnerZ</d:Pid>
            <d:LastModifiedBy><modifying user></d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T11:46:13.969</d:LastModifiedTime>
            <d:CreatedBy><creating user></d:CreatedBy>
            <d:CreatedTime>2021-03-16T11:46:13.969</d:CreatedTime>
   </m:properties>
</content>
```

> ### Note:  
> If you want to read `AuthorizedUsers` with a filter expression containing `user` values, such as `/AuthorizedUser?$filter=User eq 'myuser'`, you must always use lowercase characters \(Locale.English\) for the `user` value.



<a name="loio47b69992cd944e93903d46d700ec682f__section_wws_3k5_r4b"/>

## Create and Get a String Parameter


<table>
<tr>
<th valign="top">

Purpose

</th>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

Create String parameter.

</td>
<td valign="top">

POST

</td>
<td valign="top">

`/StringParameters` 

</td>
</tr>
<tr>
<td valign="top">

Get String parameter.

</td>
<td valign="top">

GET

</td>
<td valign="top">

`/StringParameters` 

</td>
</tr>
</table>

Assume that you like to create a String parameter `ReceiverAddress` that contains the endpoint address of a receiver system called byCloud Integration .

To create the String parameter, perform a POST request to the following address:

`https://<host address>/api/v1/StringParameters?user=myuser`

> ### Note:  
> The custom query option `user` is optional, but recommended if a technical user is used for the communication. The query option user is the logged-in user of the system that initiates the call.

Assume that you like to create a String parameter with the following attributes:

-   Pid: `PartnerZ`

-   Id: `ReceiverAddress`

-   Value: `http://receiverZ.receiver_org.com`


Provide the following request body:

```
{
  "Pid": "PartnerZ",
  "Id": "ReceiverAddress",
  "Value": "http://receiverZ.receiver_org.com"
}
```

As a response, you get a message that contains the following part:

```
<content type="application/xml">
  <m:properties>
            <d:Pid>PartnerZ</d:Pid>
            <d:Id>ReceiverAddress</d:Id>
            <d:LastModifiedBy>myuser</d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T11:25:07.916</d:LastModifiedTime>
            <d:CreatedBy>myuser</d:CreatedBy>
            <d:CreatedTime>2021-03-16T11:25:07.916</d:CreatedTime>
            <d:Value>http://receiverZ.receiver_org.com</d:Value>
  </m:properties>
</content>
```

You've the several options to read a String parameter.

To read String parameters associated with a partner with Pid `PartnerZ`, perform the following GET request:

`https://<host address>/api/v1/StringParameters?$filter=Pid eq 'PartnerZ'`

> ### Note:  
> For better readability, the URI `https://<host address>/api/v1/StringParameters?$filter=Pid eq 'PartnerZ'` isn't URI encoded. The correct URI is `https://appl-tmn.avt.hana.ondemand.com/api/v1/StringParameters$filter=Pid%20eq%20%27PartnerZ%27`.

As a response, you get a message that contains the following part:

```

<content type="application/xml">
    <m:properties>
                <d:Pid>PartnerZ</d:Pid>
                <d:Id>ReceiverAddress</d:Id>
                <d:LastModifiedBy>myuser</d:LastModifiedBy>
                <d:LastModifiedTime>2021-03-16T12:06:08.856</d:LastModifiedTime>
                <d:CreatedBy>myuser</d:CreatedBy>
                <d:CreatedTime>2021-03-16T12:06:08.856</d:CreatedTime>
                <d:Value>http://receiverZ.receiver_org.com</d:Value>
    </m:properties>
</content>
```

To read String parameters with paging and select, you can perform the following GET request:

`https://<host address>/api/v1/StringParameters?$select=Value`

As response, you get a message with one item per String parameter. Each item contains a part such like:

```
<entry>
        <id>https://<host address>/api/v1/StringParameters(Pid='PartnerZ',Id='ReceiverAddress')</id>
        <title type="text">StringParameters</title>
        <updated>2021-03-16T12:27:14.51Z</updated>
        <category term="com.sap.hci.api.StringParameter" scheme="http://schemas.microsoft.com/ado/2007/08/dataservices/scheme"/>
        <link href="StringParameters(Pid='PartnerZ',Id='ReceiverAddress')" rel="edit" title="StringParameter"/>
        <content type="application/xml">
            <m:properties>
                <d:Value>http://receiverZ.receiver_org.com</d:Value>
            </m:properties>
        </content>
</entry>
```

This GET request selects only the value field content of the first 1000 string parameter entities. To get the next 1000 entries, you've to call:

`https://<host address>/api/v1/StringParameters?$select=Value&$format=json&$skiptoken=1000`

The paging size for binary parameters is 30.

The following GET request reads the single entity by key values:

`https://<tmn>/api/v1/StringParameters(Pid='PartnerZ',Id='ReceiverAddress')`

As response, you get with one item with the following part:

```
<m:properties>
            <d:Pid>PartnerZ</d:Pid>
            <d:Id>ReceiverAddress</d:Id>
            <d:LastModifiedBy>myuser</d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T12:06:08.856</d:LastModifiedTime>
            <d:CreatedBy>myuser</d:CreatedBy>
            <d:CreatedTime>2021-03-16T12:06:08.856</d:CreatedTime>
            <d:Value>http://receiverZ.receiver_org.com</d:Value>
</m:properties>
```

For more information, check out the following SAP Community blog: [Cloud Integration – Partner Directory – Step-by-Step Example](https://blogs.sap.com/2017/07/25/cloud-integration-partner-directory-step-by-step-example/).



<a name="loio47b69992cd944e93903d46d700ec682f__section_ayd_xwv_41b"/>

## Create Binary Parameter


<table>
<tr>
<th valign="top">

Purpose

</th>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

Create Binary parameter.

</td>
<td valign="top">

POST

</td>
<td valign="top">

`/BinaryParameters` 

</td>
</tr>
</table>

Assume that you like to create a Binary parameter `MyUser` that is to be associated to partner with Pid `PartnerZ`.

Perform a POST request to the following address:

`https://<host address>/api/v1/BinaryParameters`

Provide the following request body:

```
{
  "Pid": "PartnerZ",
  "Id": "Z_XSD",
  "ContentType": "xsd",
  "Value": "PHhzOnNjaGVtYSBhdHRy2R1Y3RzIj4KICAgIDx4czpj ....."
}
```

As `Value`, in our example provide a base64-encoded XSD file.

As response, you get:

```
<m:properties>
            <d:Pid>PartnerZ</d:Pid>
            <d:Id>Z_XSD</d:Id>
            <d:LastModifiedBy>myuser</d:LastModifiedBy>
            <d:LastModifiedTime>2021-03-16T15:29:16.151</d:LastModifiedTime>
            <d:CreatedBy>myuser</d:CreatedBy>
            <d:CreatedTime>2021-03-16T15:29:16.151</d:CreatedTime>
            <d:ContentType>xsd</d:ContentType>
            <d:Value>PHhzOnNjaGVtYSBhdHRyaWJ1dGVGb3JtRG....M6c2NoZW1hPg==</d:Value>
</m:properties>
```

> ### Note:  
> Note that possible values for `ContentType` are: xml, xsl, xsd, json, text, zip, gz \(for GZIP files\), zlib, crt \(for DER-encoded X.509 certificate\).
> 
> The maximum length of the `Value` field is restricted to 260 KB.
> 
> The PEM-DER string of a certificate must be base64 encoded for the value field of the binary parameter in the POST or PUT request.

For more information on Binary parameters, check out the following SAP Community blog: [Cloud Integration – Partner Directory – Partner Dependent XML Structures and IDs](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/).



<a name="loio47b69992cd944e93903d46d700ec682f__section_ysw_syf_npb"/>

## Update Authorized User


<table>
<tr>
<th valign="top">

Purpose

</th>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

Update binary parameter.

</td>
<td valign="top">

PUT

</td>
<td valign="top">

`/BinaryParameters(Pid='partner1',Id='bp1')?user=userXYZ` 

</td>
</tr>
</table>

To update a binary parameter associated with user `userXYZ`, perform a PUT request to the following address:

`https://<host address>/api/v1/BinaryParameters(Pid='partner1',Id='bp1')?user=userXYZ`

Provide the following request body:

```
{
  "ContentType": "string",
  "Value": "string"
}
```

