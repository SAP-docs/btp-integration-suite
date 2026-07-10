<!-- loiod3af635f24a4458599eb37a1c042189d -->

# AS2 Adapter

You use the AS2 adapter to exchange business documents with your partner using the AS2 protocol. You can use this adapter to encrypt/decrypt, compress/decompress, and sign/verify the documents.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> If you \(the tenant admin\) want to provision the message broker to use AS2 adapter scenarios, you must have the Enterprise Edition license. You have to set up a cluster to use the message broker. For more information, see[Activate Enterprise Messaging](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/activating-enterprise-messaging?locale=en-US&version=Cloud) .

> ### Note:  
> There are certain limitations with regard to the usage of JMS resources.
> 
> More information: [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md)

> ### Caution:  
> Do not use this adapter type together with *Data Store Operations* steps, *Aggregator* steps, or global variables, as this can cause issues related to transactional behavior.

> ### Note:  
> When you deploy an integration flow with AS2/ AS2 MDN adapter, you can see the endpoint information of this integration flow in *Manage Integration Content* section of the operations view.

**Related Information**  


[Configure the AS2 Sender Adapter](configure-the-as2-sender-adapter-5d7ee17.md "")

[Configure the AS2 Receiver Adapter](configure-the-as2-receiver-adapter-9db62be.md "")

