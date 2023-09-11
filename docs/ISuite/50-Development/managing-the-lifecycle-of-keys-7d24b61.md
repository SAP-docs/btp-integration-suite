<!-- loio7d24b61c989e4fa5851797fe391e83d2 -->

# Managing the Lifecycle of Keys

To enable secure communication between the tenant and connected remote systems, the system keystore that is deployed on the tenant must contain the up-to-date keys owned by the tenant administrator and SAP.



<a name="loio7d24b61c989e4fa5851797fe391e83d2__context_njs_1vy_wbb"/>

## Context



### 

SAP Integration Suite comes with a set of features that facilitate the tenant administrator's task of renewing keys provided by SAP on the tenant.

The following different keystore types enable the tenant administrator to renew keys in an efficient way:

-   System keystore

    This keystore is located in the `system.jks` file provided with the tenant and contains all keys that are actively used by the deployed integration flows.

-   New SAP Keys keystore

    This keystore contains keys already prepared by SAP before a key pair expires.

    As the key expiry date approaches, the tenant administrator can do the following:

    -   Download the new SAP keys from the KeyRenewal keystore to share them with the administrators of the connected back ends

    -   Activate the keys relevant for the tenant


-   SAP Key History keystore

    This keystore contains old \(expired\) keys.

    If required, the tenant administrator can restore a key from the Key History keystore and use it to replace a key in the system keystore.


During the activation of an SAP key, the system performs three steps, as shown in the following figure.

![](../40-RemoteSystems/images/Cloud_Integration_Certificate_Management_Activating_SAP_Keys_fbe4f91.png)

1.  The old key pair \(which expires soon\) is added by the system to the Key History keystore.

2.  The old key pair \(in the system.jks keystore\) is overwritten by the new key pair from the New SAP Keys keystore.

3.  In the New SAP Keys keystore, the new key pair is removed.


> ### Note:  
> To restore an old key pair, the tenant administrator can copy the key pair from the SAP Key History keystore to the New Keys keystore and activate it there.

**Related Information**  


[Activating a New Key Pair Provided by SAP](activating-a-new-key-pair-provided-by-sap-383be7a.md "Activate a new key pair provided by SAP in order to replace an old key pair which is supposed to expire soon.")

[Restoring a Key Pair from the Key History](restoring-a-key-pair-from-the-key-history-43965e7.md "Restore a key pair from the SAP Key History.")

[Renewal of Keys Provided by SAP](../40-RemoteSystems/renewal-of-keys-provided-by-sap-5db16f5.md "To enable secure communication between the tenant and connected remote systems, the system keystore deployed on the tenant must contain up-to-date keys owned by the tenant administrator and SAP.")

