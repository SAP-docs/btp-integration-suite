<!-- loio0800f7bac2cd490d8fdf8b7fedec9b2a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Copying Keystore Entries in Edge Integration Cell

The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries \(X.509 certificates and key pairs\).

> ### Note:  
> For details on the list view as well as on how to create, add, or upload security artifacts, see: [Managing Keystore Entries](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-keystore-entries?version=CLOUD&q=keystore).

> ### Note:  
> You can assign a runtime to one keystore only, but you can assign a keystore to several runtimes. If you assign only one runtime to an exiting keystore, this keystore is only available for this single runtime.
> 
> Remember:
> 
> -   The maximum size of a keystore assigned to an edge runtime is 1 MB.
> 
> -   The maximum number of keystores is limited to 20 per tenant.
> 
> -   You can assign up to 20 runtimes to a keystore.

> ### Caution:  
> To change the existing assignment of a keystore to a specific runtime, can cause message processing failures.

For Edge Integration Cell, you have the option *Copy to Keystore* that allows you to copy a selected artifact into another keystore. Go to the artifact, in the *Actions* section, select the more icon \(<span class="SAP-icons-V5"></span>\) and click on *Copy to Keystore*.

Fill in the following information:


<table>
<tr>
<td valign="top">

*Source Alias*

</td>
<td valign="top">

Source alias ready to be copied.

This field is pre-filled and not editable. If you want to change the source alias, cancel the current process and select a different artifact.

</td>
</tr>
<tr>
<td valign="top">

*Target Alias*

</td>
<td valign="top">

Enter a name for the copied artifact.

This field is pre-filled with the information from the source alias.

</td>
</tr>
<tr>
<td valign="top">

*Source Keystore*

</td>
<td valign="top">

Source Keystore from where you copy the existing artifact.

This field is pre-filled and not editable.

</td>
</tr>
<tr>
<td valign="top">

*Target Keystore*

</td>
<td valign="top">

Select an existing keystore you want the artifact to copy in from the drop-down.

</td>
</tr>
<tr>
<td valign="top">

*Overwrite Existing Entry*

</td>
<td valign="top">

Check to allow the overwriting of existing entries.

If you don’t select this option while choosing a name that already exist in your target keystore, an error message is thrown.

</td>
</tr>
</table>



<a name="loio0800f7bac2cd490d8fdf8b7fedec9b2a__section_bhs_wrq_nyb"/>

## Working with Security Artifacts

For Edge Integration Cell, there are certain things to consider when working with security artifacts. For more information, see [Edge Integration Cell Runtime Scope](edge-integration-cell-runtime-scope-144c64a.md).

