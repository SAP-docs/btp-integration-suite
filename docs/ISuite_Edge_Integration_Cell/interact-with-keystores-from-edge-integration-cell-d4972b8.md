<!-- loiod4972b8ce9b140b0afab5d7af3ee098f -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Interact with Keystores from Edge Integration Cell

A keystore is used to secure message exchange both at transport level and at message level. For Edge Integration Cell, since you can have more than one keystore, you can decide whether to create a new, add, remove, or delete an existing keystore.

> ### Note:  
> For more general information on keystore functionalities, see: [Keystore](https://help.sap.com/docs/integration-suite/sap-integration-suite/keystore?version=CLOUD&q=keystore) 



<a name="loiod4972b8ce9b140b0afab5d7af3ee098f__section_pnt_ztq_nyb"/>

## Adding a Keystore to a Runtime

Perform the following steps to add an existing keystore to your runtime.

1.  Access the associated *Keystore* via *Monitor* \> *Keystore* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select your respective runtime to which you want to add the keystore.

    > ### Note:  
    > You can either create a new keystore and assign the runtime to it or you can assign the runtime to an existing keystore. Consider the following limitations:
    > 
    > You can assign up to 20 runtimes to a single keystore.
    > 
    > The maximum permissible size for a keystore, which an edge runtime is assigned to, is 1 MB.
    > 
    > While a runtime can only be assigned to one keystore, a single keystore can accommodate multiple runtimes.
    > 
    > If an existing keystore is utilized again, shared access will be granted to all runtimes assigned to it.
    > 
    > The keystore becomes exclusive to a particular runtime if only one runtime is assigned to it.
    > 
    > You can assign a runtime to the SAP pre-delivered or *system* keystore, given that its size doesn't exceed the 1 MB restriction.

    > ### Caution:  
    > To change the existing assignment of a keystore to a specific runtime, can cause message processing failures.

3.  Select *Add* and provide the following details:


    <table>
    <tr>
    <td valign="top">
    
    *Keystore*
    
    </td>
    <td valign="top">
    
    From the drop-down list, select the keystore.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtime*
    
    </td>
    <td valign="top">
    
    Depending on the runtime-specfic view you've chosen, this field is prefilled.
    
    </td>
    </tr>
    </table>
    
4.  Select *Add* to assign the keystore to the selected runtime.

5.  Your keystore is being added. Refresh the table view to get an updated status.




<a name="loiod4972b8ce9b140b0afab5d7af3ee098f__section_lx4_bwq_nyb"/>

## Creating a New Keystore

Perform the following steps to create a new keystore.

1.  Access the associated *Keystore* via *Monitor* \> *Keystore* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select the *All* view.

    > ### Note:  
    > Each runtime can only have one associated keystore; one keystore, however, can be associated with up to 20 runtimes. So, after the removal, the keystore is still available and may still be associated with other runtimes.

3.  Select *Create* and provide the following details:


    <table>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Provide a name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtime*
    
    </td>
    <td valign="top">
    
    Select one or more runtimes associated with this keystore.
    
    </td>
    </tr>
    </table>
    
4.  Select *Deploy* to assign the keystore to the selected runtime.

5.  Your new keystore is added to the list. Refresh the table view to get an updated status.




<a name="loiod4972b8ce9b140b0afab5d7af3ee098f__section_cbz_ctq_nyb"/>

## Removing a Keystore

Perform the following steps to remove a keystore from one runtime only.

> ### Note:  
> Each runtime can only have one associated keystore; one keystore, however, can be associated with up to 20 runtimes. So, after the removal, the keystore is still available and may still be associated with other runtimes.

1.  Access the associated *Keystore* via *Monitor* \> *Keystore* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select your respective runtime from which you want to remove the keystore.

3.  From the section *Action*, select the removal icon \(<span class="SAP-icons-V5"></span>\) to remove your keystore.

    > ### Caution:  
    > Removing the keystore might cause problems to associated integration flows.

4.  Confirm that you want to remove the keystore. Select *Confirm*.

5.  Your keystore is being removed. Refresh the table view to get an updated status.




<a name="loiod4972b8ce9b140b0afab5d7af3ee098f__section_gwj_ttq_nyb"/>

## Deleting a Keystore

Perform the following steps to delete a keystore from your tenant in Edge Integration Cell for good and cut the assignment to any runtime.

1.  Access the associated *Keystore* via *Monitor* \> *Keystore* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select *All*. Other than the runtime-specific view, only this view allows you to access the delete option.

3.  From the section *Action*, select the bin icon \(:wastebasket:\) to delete your keystore.

    > ### Caution:  
    > The deletion of a keystore can't be undone and will eventually affect deployed integration flows associated with the keystore.

4.  Confirm that you want to remove the keystore. Select *Confirm*.

5.  Your keystore is being deleted. Refresh the table view to get an updated status.


