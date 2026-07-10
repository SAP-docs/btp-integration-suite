<!-- loio98da76c5d29348498e8b9e22ded9c028 -->

# Ariba Adapter

You use this procedure to configure a sender and receiver channel of an integration flow with the Ariba Network adapter. These channels enable the SAP and non-SAP cloud applications to send and receive business-specific documents in cXML format to and from the Ariba Network. Examples of business documents are purchase orders and invoices.

> ### Restriction:  
> An integration flow you deploy in SAP Cloud Integration deploys in multiple IFLMAP worker nodes. Polling is triggered from only one of the worker nodes. The message monitoring currently displays the process status from the worker nodes where the *Scheduler* is not started. This results in the message monitor displaying messages with less than a few milliseconds, where the schedule was not triggered. These entries contain *firenow=true* in the log. You can ignore these entries.

**Related Information**  


[Configure the Ariba Sender Adapter](configure-the-ariba-sender-adapter-0629b58.md "The Ariba sender adapter connects SAP Integration Suite to the Ariba Network. Using this adapter, SAP and non-SAP cloud applications can receive business-specific documents in commerce eXtensible Markup Language (cXML) format from the Ariba network. The sender adapter allows you to define a schedule for polling data from Ariba.")

[Configure the Ariba Receiver Adapter](configure-the-ariba-receiver-adapter-49dffa3.md "The Ariva receiver adapter connects SAP Integration Suite to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language (cXML) format to the Ariba network.")

