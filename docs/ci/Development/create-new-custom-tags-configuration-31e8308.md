<!-- loio31e830841ace4ab08b1c586e910c47c0 -->

# Create New Custom Tags Configuration



To create custom tags, you need to perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
<th valign="top">

Purpose

</th>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

`​/CustomTagConfigurations` 

</td>
<td valign="top">

Create custom tags.

</td>
</tr>
</table>

As request body, provide the following JSON content:

```
{
"CustomTagsConfigurationContent": "<base64-encoded custom tag configurations content>"
}

```

Assume that you like to create a mandatory custom tag with the name *Owner*.

The related JSON representation is:

```
{"customTagsConfiguration":[{"tagName":"Owner","isMandatory":true}]}
```

After base64 encoding, you get the following string:

`eyJjdXN0b21UYWdzQ29uZmlndXJhdGlvbiI6W3sidGFnTmFtZSI6Ik93bmVyIiwiaXNNYW5kYXRvcnkiOnRydWV9XX0=`

Send the following POST request:

`https://<host address>/api/v1/CustomTagConfigurations`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As request body, send:

```
{
"CustomTagsConfigurationContent": "eyJjdXN0b21UYWdzQ29uZmlndXJhdGlvbiI6W3sidGFnTmFtZSI6Ik93bmVyIiwiaXNNYW5kYXRvcnkiOnRydWV9XX0="
}

```

If a custom tags configuration is already available on the tenant, add the following query parameter to the request:

`Overwrite=true`

