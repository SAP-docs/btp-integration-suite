<!-- loio39eb10185fba4dc9945977e493a3d5e8 -->

# Manage Keystore for Edge Integration Cell

A keystore is used to secure message exchange both at transport level and at message level.



<a name="loio39eb10185fba4dc9945977e493a3d5e8__section_itm_qlx_bzb"/>

## General Information

For Edge Integration Cell, you can have multiple keystores to separate the artifact assignment for the different runtimes.

For more general information on keystore functionalities, see [Keystore](40-RemoteSystems/keystore-b163513.md).

> ### Note:  
> For Edge Integration Cell, there are specific security artifact conditions in place. For more information, see [Copying Keystore Entries in Edge Integration Cell](copying-keystore-entries-in-edge-integration-cell-0800f7b.md)

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



<a name="loio39eb10185fba4dc9945977e493a3d5e8__section_gpl_44q_nyb"/>

## Keystore Details View

For Edge Integration Cell, access the associated Keystore via *Monitor* \> *Keystore* under *Manage Security*.

> ### Note:  
> Make sure to select the correct runtime by clicking on the drop-down menu in the upper left corner of your screen. Depending on the selected runtime, you get different viewing results and actions:
> 
> -   *All View*: Shows all keystores in a combined list. This view allows you to edit keystores by updating its runtimes, as well as to delete keystores. 
> 
> -   *Runtime-Specific View*: Shows your keystores associated with your specific runtime. This view allows you to remove keystores from runtimes.
> 
> 
> For more information, see: [Manage Security for Edge Integration Cell](manage-security-for-edge-integration-cell-1783cf8.md).

After you’ve specified the runtime view, check the details view list with the following information:


<table>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of the keystore.

</td>
</tr>
<tr>
<td valign="top">

*Entries*

</td>
<td valign="top">

Number of associated entries within the keystore.

</td>
</tr>
<tr>
<td valign="top">

*Runtimes*

</td>
<td valign="top">

Number of runtimes associated with the keystore.

> ### Note:  
> Each runtime can only have one associated keystore; one keystore, however, can be associated with up to 20 runtimes.



</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Current status of the keystore. Click *Refresh* to update the status of each key store, for example, after you’ve made changes.

> ### Note:  
> If you have more than one runtime associated with one keystore, the overall status is an aggregated status that is a combined status of the individual associated runtimes.

Have a look at the following example:

If the status of **Runtime1** is *Deployed*, while the status of **Runtime2** is *Runtime Deactivated*, the aggregated status in the list shows *Runtime Deactivated*.

Click on the number displayed in the list to get a detailed view of your different runtimes.

The following statuses are possible:

-   *Deployed*: Keystore is up and running.

-   *Stored*: Keystore is deployed already but not yet synchronized with the associated runtime.

-   *Removal Initiated*: The process of removing the keystore from the runtime is in progress. 

-   *Deletion Initiated*: Deletion of the keystore has been initiated.

-   *Runtime Inactive*

-   *Error*




</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

Depending on your Runtime view, you get different options:

Choose any runtime-specific view to:

-   *Add*: Add a keystore to the runtime.

-   *Remove*: Select to remove the keystore from the runtime.


Choose the *All* view to:

-   *Edit*: Add or remove associated runtimes.

-   *Delete*: Select the delete the keystore permanently.


For more information, see: [Interact with Keystores from Edge Integration Cell](interact-with-keystores-from-edge-integration-cell-d4972b8.md).

</td>
</tr>
</table>

To access the security artifacts associated with your keystore, select the keystore by clicking on it. A detail view opens to the right.

For more information, see: [Copying Keystore Entries in Edge Integration Cell](copying-keystore-entries-in-edge-integration-cell-0800f7b.md).

**Related Information**  


[Interact with Keystores from Edge Integration Cell](interact-with-keystores-from-edge-integration-cell-d4972b8.md "A keystore is used to secure message exchange both at transport level and at message level. For Edge Integration Cell, since you can have more than one keystore, you can decide whether to create a new, add, remove, or delete an existing keystore.")

[Copying Keystore Entries in Edge Integration Cell](copying-keystore-entries-in-edge-integration-cell-0800f7b.md "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).")

