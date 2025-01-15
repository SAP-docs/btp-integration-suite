<!-- loio3baec7dcfd2e46bb8764d746211c4d32 -->

# Manage PGP Keyrings for Edge Integration Cell

PGP Keyrings are required to support message level security based on PGP Standard.



<a name="loio3baec7dcfd2e46bb8764d746211c4d32__section_itm_qlx_bzb"/>

## General Information

PGP Keyrings come with two types of artifacts. For Edge Integration Cell, you can have multiple keyrings to separate the artifact assignment for the different runtimes.

For more general information on keyring functionalities, see [PGP Keys](40-RemoteSystems/pgp-keys-9e7e8f9.md).

> ### Note:  
> For details on the list view and how to create, add, or upload PGP key material, see [Managing PGP Keys](50-Development/managing-pgp-keys-cd478a7.md)

> ### Note:  
> You can assign a runtime to one keyring only, but you can assign a keyring to several runtimes. If you assign only one runtime to an exiting keyring, this keyring is only available for this single runtime.
> 
> Remember:
> 
> -   The maximum size of a keyring assigned to an edge runtime is 1 MB.
> 
> -   The maximum number of keyrings is limited to 20 per tenant.
> 
> -   You can assign up to 20 runtimes to a keyring.

> ### Caution:  
> To change the existing assignment of a keyring to a specific runtime, can cause message processing failures.

> ### Note:  
> Keyring artifacts have two different types: PGP *Public Keyring* and PGP*Secret Keyring*. Keyrings of both types are displayed together in a single list. However, they are handled independently. For example, a runtime can be assigned to both a Public Keyring and a Secret Keyring simultaneously.



<a name="loio3baec7dcfd2e46bb8764d746211c4d32__section_gpl_44q_nyb"/>

## Keyring Details View

For Edge Integration Cell, access the associated Secret and Public Keyring via *Monitor* \> *PGP Keys* under *Manage Security*.

> ### Note:  
> Make sure to select the correct runtime by clicking on the drop-down menu in the upper left corner of your screen. Depending on the selected runtime, you get different viewing results and actions:
> 
> -   *All View*: Shows all keyrings in a combined list. This view allows you to edit keyrings by updating its runtimes, as well as to delete keyrings. 
> 
> -   *Runtime-Specific View*: Shows your keyrings associated with your specific runtime. This view allows you to remove keyrings from runtimes.
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

Name of the keyring.

</td>
</tr>
<tr>
<td valign="top">

*Runtimes*

</td>
<td valign="top">

Number of runtimes associated with the keyring.

> ### Note:  
> Each runtime can only have one associated keyring; one keyring, however, can be associated with up to 20 runtimes.



</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Current status of the keyring. Select *Refresh* to update the status of each keyring, for example, after you’ve made changes.

> ### Note:  
> If you have more than one runtime associated with one keyring, the overall status is an aggregated status that is a combined status of the individual associated runtimes.

Have a look at the following example:

If the status of **Runtime1** is *Deployed*, while the status of **Runtime2** is *Runtime Deactivated*, the aggregated status in the list shows *Runtime Deactivated*.

Click on the number displayed in the list to get a detailed view of your different runtimes.

The following statuses are possible:

-   *Deployed*: Keyring is up and running.

-   *Stored*: Keyring is deployed already but not yet synchronized with the associated runtime.

-   *Removal Initiated*: The process of removing the keyring from the runtime is in progress. 

-   *Deletion Initiated*: Deletion of the keyring has been initiated.

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

-   *Add*: Add a keyring to the runtime.

-   *Remove*: Select to remove the keyring from the runtime.


Choose the *All* view to:

-   *Edit*: Add or remove associated runtimes.

-   *Delete*: Select the delete the keyring permanently.


For more information, see: [Interact with Keystores from Edge Integration Cell](interact-with-keystores-from-edge-integration-cell-d4972b8.md).

</td>
</tr>
</table>

To access the security artifacts associated with your keyring, select the keyring by clicking on it. A detail view opens to the right.

**Related Information**  


[Interact with Keystores from Edge Integration Cell](interact-with-keystores-from-edge-integration-cell-d4972b8.md "A keystore is used to secure message exchange both at transport level and at message level. For Edge Integration Cell, since you can have more than one keystore, you can decide whether to create a new, add, remove, or delete an existing keystore.")

