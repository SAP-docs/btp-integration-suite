<!-- loio383be7ad9c8840e38facf9323619907b -->

# Activating a New Key Pair Provided by SAP

Activate a new key pair provided by SAP in order to replace an old key pair which is supposed to expire soon.



## Context

> ### Caution:  
> Make sure that you activate a new SAP key pair as part of a dedicated key renewal process that you have agreed on with the administrators of all connected sender and receiver systems.
> 
> For more information on the recommended processes, see the separate topics.

> ### Note:  
> Note regarding the case if you don’t renew an SAP key prior to its expiration date:
> 
> A system job makes sure that in this case the new key is automatically activated \(one day before the expiration date\).
> 
> This job checks daily if there are new entries in the New SAP Keys keystore and if an SAP key pair entry in the system keystore \(system.jks\) is due to expire within the next 24 hours. If this is the case, the job checks whether the New SAP Keys keystore contains an entry with the same alias. If this is the case, the key pair entry is activated \(through the same sequence of steps as shown in the figure\).



## Procedure

1.  Go to the *Monitor* section and select the *Keystore* tile \(under *Manage Security*\).

2.  Choose the *New SAP Keys* tab.

3.  Select the entry and choose *Activate*.


**Related Information**  


[Renewal of Keys Provided by SAP](../40-RemoteSystems/renewal-of-keys-provided-by-sap-5db16f5.md "To enable secure communication between the tenant and connected remote systems, the system keystore deployed on the tenant must contain up-to-date keys owned by the tenant administrator and SAP.")

[Activating a New SAP Key Pair on the Tenant](../40-RemoteSystems/activating-a-new-sap-key-pair-on-the-tenant-ada2969.md "")

