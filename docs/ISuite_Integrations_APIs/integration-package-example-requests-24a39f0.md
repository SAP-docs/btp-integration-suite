<!-- loio24a39f0a9e5b44238b194c55ec390aaa -->

# Integration Package Example Requests

You can copy integration packages to your *Design* space. You can also create, update, delete, and search for integration packages in design time.



<a name="loio24a39f0a9e5b44238b194c55ec390aaa__section_dpm_nmw_z4b"/>

## Import an Integration Package into the Design Section

To import an integration package into the *Design* section, send the following call:


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

`/IntegrationPackages` 

</td>
</tr>
</table>

Provide the following request body:

```

{
"PackageContent":<base64-encoded package content>
}
```

If the package to be imported is in zip format, it has to be converted into **base 64 encoded** format.

> ### Note:  
> You can't import a package if there's already a package in the *Design* section with the same name. You can use the `Overwrite` parameter to overwrite the existing package. Use the following request:
> 
> `https://<host address>/api/v1/IntegrationPackages?Overwrite=true`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).



<a name="loio24a39f0a9e5b44238b194c55ec390aaa__section_wws_3k5_r4b"/>

## Download an Integration Package

To download an integration package as `.zip` file from the *Design* section, send the following call:


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

`/IntegrationPackages('{Id}')/$value` 

</td>
</tr>
</table>

> ### Note:  
> Download fails if the package contains one or more artifacts in draft state.

