<!-- loio5db16f58ec6947698168ce27f3361a80 -->

# Renewal of Keys Provided by SAP

To enable secure communication between the tenant and connected remote systems, the system keystore deployed on the tenant must contain up-to-date keys owned by the tenant administrator and SAP.



The certificate management features of the Web UI support the key renewal process described below.

> ### Caution:  
> You must exercise caution when renewing keys in order to avoid unplanned downtimes of your integration scenarios.
> 
> The tenant administrator has to orchestrate the key renewal process together with the administrators of all involved sender and receiver systems. It may be necessary, for example, to agree on a specific downtime in certain cases.
> 
> Note that it is the tenant administrator who should coordinate the whole process, as he or she knows all the administrators of the connected sender and receiver systems.
> 
> Downtime can be avoided in certain cases. In order to schedule and set up a key renewal process correctly, see the topics linked below.
> 
> We provide an example of a renewal process in a separate topic.

1.  SAP prepares the new key pair 60 days before a key expires. The new key pair is imported into the customer tenant by SAP.

    The new key pair has the same alias as the key pair that is due to expire.

2.  The tenant administrator can access the content of this keystore.

    To do this, go to section *Monitor* \> *Integrations and APIs* and select *Keystore* \(under *Manage Security*\). Then, select *New SAP Keys*.

3.  SAP informs the tenant administrator about the new key.

4.  Shortly before the key expires, the tenant administrator downloads the X.509 certificate and certificate chain of the new key pair from the New SAP Keys keystore.

    To do this, go to section *Monitor* \> *Integrations and APIs* and select *Keystore* \(under *Manage Security*\). Then, select *New SAP Keys*.

5.  The tenant administrator informs the administrators of the connected sender and receiver systems that keys need to be renewed. If required, the administrators of the sender and receiver systems and the tenant administrator agree on a downtime during which the affected keys can be exchanged both in the sender and receiver systems and on the tenant.

6.  The administrators of the sender and receiver systems update the keystores of their systems using the new certificate and certificate chain \(provided to them by the tenant administrator\).

    The tenant administrator activates the new key pair on the tenant with the certificate management features of the Web UI.


**Related Information**  


[Keys Provided by SAP](keys-provided-by-sap-9d8a60b.md "")

[Activating a New SAP Key Pair on the Tenant](activating-a-new-sap-key-pair-on-the-tenant-ada2969.md "")

[Example: Renewal of Key Pairs Provided by SAP \(Avoiding Downtime\)](example-renewal-of-key-pairs-provided-by-sap-avoiding-downtime-fe87373.md "")

[Renewal of SAP Keys Without Any Downtime](renewal-of-sap-keys-without-any-downtime-2218fa4.md "")

