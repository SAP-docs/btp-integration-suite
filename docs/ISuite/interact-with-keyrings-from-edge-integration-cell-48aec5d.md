<!-- loio48aec5d54b1146b4a32455e4616423e8 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Interact with Keyrings from Edge Integration Cell

PGP Keyrings are required to support message level security based on PGP Standard. For Edge Integration Cell, since you can have more than one keyring, you can decide whether to create a new, add, remove, or delete an existing keyring.

> ### Note:  
> For more general information on keyring functionalities, see: [PGP Keys](40-RemoteSystems/pgp-keys-9e7e8f9.md).

> ### Note:  
> The *pubring* and *secring* keyrings are considered default keyring artifacts. They are always displayed in the keyring list, cannot be deleted, and remain permanently assigned to the runtime cloudintegration. However, you can still assign additional runtimes as needed.



<a name="loio48aec5d54b1146b4a32455e4616423e8__section_pnt_ztq_nyb"/>

## Adding a Keyring to a Runtime

Perform the following steps to add an existing keyring to your runtime.

1.  Access the associated *Keyring* via *Monitor* \> *PGP Keys* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select your respective runtime to which you want to add the keyring.

    > ### Note:  
    > You can either create a new keyring and assign the runtime to it or you can assign the runtime to an existing keyring. Consider the following limitations:
    > 
    > You can assign up to 20 runtimes to a single keyring.
    > 
    > The maximum permissible size for a keyring, which an edge runtime is assigned to, is 1 MB.
    > 
    > While a runtime can only be assigned to one keyring, a single keyring can accommodate multiple runtimes.
    > 
    > If an existing keyring is utilized again, shared access will be granted to all runtimes assigned to it.
    > 
    > The keyring becomes exclusive to a particular runtime if only one runtime is assigned to it.

    > ### Caution:  
    > To change the existing assignment of a keyring to a specific runtime, can cause message processing failures.

3.  Select *Add* and provide the following details:


    <table>
    <tr>
    <td valign="top">
    
    *Keyring*
    
    </td>
    <td valign="top">
    
    From the drop-down list, select the keyring.
    
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
    
4.  Select *Add* to assign the keyring to the selected runtime.

5.  Your keyring is being added. Refresh the table view to get an updated status.




<a name="loio48aec5d54b1146b4a32455e4616423e8__section_lx4_bwq_nyb"/>

## Creating a New Keyring

Perform the following steps to create a new keyring.

1.  Access the associated *Keyring* via *Monitor* \> *PGP Keys* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select the *All* view.

    > ### Note:  
    > Each runtime can only have one associated keyring; one keyring, however, can be associated with up to 20 runtimes. So, after the removal, the keyring is still available and may still be associated with other runtimes.

3.  Select *Create* and provide the following details:


    <table>
    <tr>
    <td valign="top">
    
    *Keyring Name*
    
    </td>
    <td valign="top">
    
    Provide a name.

    > ### Remember:  
    > When creating new keyrings, you must follow the following naming conventions:
    > 
    > -   Public Keyrings: The name must start with `pubring-`
    > 
    > -   Secret Keyrings: The name must start with `secring-`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Keyring File*
    
    </td>
    <td valign="top">
    
    Choose the file containing the content to be imported into the new keyring.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Passphrase* \(only for Secret Keyrings\)
    
    </td>
    <td valign="top">
    
    Enter the passphrase of he keyring file being uploaded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtime*
    
    </td>
    <td valign="top">
    
    Select one or more runtimes associated with this keyring.
    
    </td>
    </tr>
    </table>
    
4.  Select *Deploy* to assign the keyring to the selected runtime.

5.  Your new keyring is added to the list. Refresh the table view to get an updated status.




<a name="loio48aec5d54b1146b4a32455e4616423e8__section_cbz_ctq_nyb"/>

## Removing a keyring

Perform the following steps to remove a keyring from one runtime only.

> ### Note:  
> Each runtime can only have one associated keyring; one keyring, however, can be associated with up to 20 runtimes. So, after the removal, the keyring is still available and may still be associated with other runtimes.

1.  Access the associated *Keyring* via *Monitor* \> *PGP Keys* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select your respective runtime from which you want to remove the keyring.

3.  From the section *Action*, select the removal icon \(<span class="SAP-icons-V5"></span>\) to remove your keyring.

    > ### Caution:  
    > Removing the keyring might cause problems to associated integration flows.

4.  Confirm that you want to remove the keyring. Select *Confirm*.

5.  Your keyring is being removed. Refresh the table view to get an updated status.




<a name="loio48aec5d54b1146b4a32455e4616423e8__section_gwj_ttq_nyb"/>

## Deleting a Keyring

Perform the following steps to delete a keyring from your tenant in Edge Integration Cell for good and cut the assignment to any runtime.

1.  Access the associated *Keyring* via *Monitor* \> *PGP Keys* in the section *Manage Security*.

2.  From the drop-down menu in the upper left corner of your screen, select *All*. Other than the runtime-specific view, only this view allows you to access the delete option.

3.  From the section *Action*, select the bin icon \(:wastebasket:\) to delete your keyring.

    > ### Caution:  
    > The deletion of a keyring can't be undone and will eventually affect deployed integration flows associated with the keyring.

4.  Confirm that you want to remove the keyring. Select *Confirm*.

5.  Your keyring is being deleted. Refresh the table view to get an updated status.


