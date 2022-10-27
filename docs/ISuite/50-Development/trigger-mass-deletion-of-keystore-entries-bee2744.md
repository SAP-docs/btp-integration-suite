<!-- loiobee27443d3ab4ec992a3203f4154bb0b -->

# Trigger Mass Deletion of Keystore Entries

Delete several entries owned by the tenant administrator from the keystore.



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

PUT



</td>
<td valign="top">

 `/KeystoreResources('system')?deleteEntries=true` 



</td>
</tr>
</table>

The aliases of the entries that you want to delete must be specified in the `Aliases` property of the request body.

For example, send the following request:

`https://<host address>/api/v1/KeystoreResources('system')?deleteEntries=true`

In the request body, provide the aliases of the entries to be deleted.

```
{"Aliases":"alias1;alias2;alias3"}
```

> ### Note:  
> -   If an alias contains the character ';', it must be escaped.
> 
>     Example:
> 
>     "Company A; Company B" -\> "Company A\\; Company B";
> 
> -   If an alias contains the character '\\', it must be escaped.
> 
>     Example:
> 
>     Alias1="Company\\A\\", Alias2="CompanyB" -\> "Aliases":"Company\\\\A\\\\;CompanyB"

