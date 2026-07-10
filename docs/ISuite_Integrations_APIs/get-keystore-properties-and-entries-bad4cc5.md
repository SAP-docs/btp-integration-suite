<!-- loiobad4cc5d2287451d964fed9327b61a4f -->

# Get Keystore Properties and Entries

Get the time when the keystore was modified last \(LastModifiedTime\) and the keystore entries of the *Current* keystore.



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

`/Keystores('system')?$expand=Entries&$select=LastModifiedTime,Entries` 

</td>
</tr>
</table>

