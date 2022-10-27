<!-- loio43965e71bc0f4581b086803b9047ad8d -->

# Restoring a Key Pair from the Key History

Restore a key pair from the SAP Key History.



## Context

You use this process to restore an entry from the SAP Key History in the New SAP Keys keystore. In a subsequent step, you can then reactivate the key to make it available in the tenant's system keystore.

> ### Caution:  
> Make sure that you activate a new SAP key pair according to the dedicated key renewal process that you have agreed with the administrators of all connected sender and receiver systems.
> 
> For more information about the recommended processes, see the separate topics.



### 



## Procedure

1.  Choose the *SAP Key History* tile in the *Manage Security Material* section.

2.  Select the entry and choose *Add to New SAP Keys*.

    In the subsequent dialog, the old SAP alias name is proposed, but you have the option to overwrite it with a new SAP alias.

    > ### Tip:  
    > You can specify a new SAP alias if you want to avoid overwriting already active key pairs with this step.


**Related Information**  


[Renewal of Keys Provided by SAP](../40-RemoteSystems/renewal-of-keys-provided-by-sap-5db16f5.md "To enable secure communication between the tenant and connected remote systems, the system keystore deployed on the tenant must contain up-to-date keys owned by the tenant administrator and SAP.")

[Activating a New SAP Key Pair on the Tenant](../40-RemoteSystems/activating-a-new-sap-key-pair-on-the-tenant-ada2969.md "")

