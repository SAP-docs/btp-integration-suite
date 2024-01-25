<!-- loiod3af635f24a4458599eb37a1c042189d -->

# AS2 Adapter

You use the AS2 adapter to exchange business documents with your partner using the AS2 protocol. You can use this adapter to encrypt/decrypt, compress/decompress, and sign/verify the documents.

> ### Note:  
> If you \(the tenant admin\) want to provision the message broker to use AS2 adapter scenarios, you must have the Enterprise Edition license. You have to set up a cluster to use the message broker. For more information, see [Activating Enterprise Messaging](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a74cddceacb34abb958e817c1f6782d2.html "Activate SAP Event Mesh.") :arrow_upper_right:.

> ### Note:  
> There are certain limitations with regard to the usage of JMS resources.
> 
> More information: [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md)

> ### Caution:  
> Do not use this adapter type together with *Data Store Operations* steps, *Aggregator* steps, or global variables, as this can cause issues related to transactional behavior.

> ### Restriction:  
> If you deploy an integration flow in SAP Cloud Integration, it deploys in multiple IFLMAP worker nodes. Polling is triggered from only one of these nodes. The message monitor displays the process status for the worker nodes in which the *Scheduler* has not started. This results in the message monitor displaying messages with less than a few milliseconds, where the scheduler was not triggered. These entries contain *firenow=true* in the log. You can ignore these entries.

> ### Note:  
> When you deploy an integration flow with AS2/ AS2 MDN adapter, you can see the endpoint information of this integration flow in *Manage Integration Content* section of the operations view.

**Related Information**  


[Configure the AS2 Sender Adapter](configure-the-as2-sender-adapter-5d7ee17.md "")

[Configure the AS2 Receiver Adapter](configure-the-as2-receiver-adapter-9db62be.md "")

