<!-- loioa9473749d6214beca8007f808ebed8ef -->

# Get Custom Tags Defined on the Tenant



To get all custom tags defined by the tenant administrator, you need to perform the following call:


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

GET



</td>
<td valign="top">

 `​/CustomTagConfigurations('CustomTags')/$value` 



</td>
<td valign="top">

Get all custom tags.



</td>
</tr>
</table>

Assume that you like to get all custom tags defined by the tenant administrator.

Send the following GET request:

`https://<host address>/api/v1/CustomTagConfigurations('CustomTags')/$value`

If a mandatory custom tag with name *Author* is defined on the tenant, you get the following response:

```
{"customTagsConfiguration":[{"tagName":"Author","isMandatory":true}]}
```

If for the mandatory custom tag with name *Author* also permitted values \(for example, `Mr. Bean` and `Ms. Bean`\) are defined, you get the following response:

```
{"customTagsConfiguration":[{"tagName":"Author","permittedValues":["Mr. Bean, Ms. Bean"],"isMandatory":true}]}
```

