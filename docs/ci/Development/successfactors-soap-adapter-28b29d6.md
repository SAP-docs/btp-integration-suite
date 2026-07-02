<!-- loio28b29d6b50d6419eadb15e59b9462da4 -->

# SuccessFactors SOAP Adapter

The SuccessFactors adapter enables you to communicate with the SuccessFactors system. You use the SOAP message protocol to connect to the SOAP-based Web services of the SuccessFactors system.

> ### Note:  
> You can now pass filter conditions via a header or property while performing an asynchronous or ad hoc operation.

> ### Restriction:  
> If you deploy an integration flow in SAP Cloud Integration, it deploys in multiple tenants. Polling is triggered from only one of these tenants. The message monitor displays the process status for the tenants where the *Scheduler* has not started. As a result, the message monitor displays messages of less than a few milliseconds, where the scheduler was not triggered. These entries contain *firenow=true* in the log. You can ignore these entries.

> ### Remember:  
> You must enable *HTTP Session Reuse* with either the *On Exchange* or *On Integration Flow* level.
> 
> For more information, see [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

**Related Information**  


[Configure the SuccessFactors \(SOAP\) Sender Adapter](configure-the-successfactors-soap-sender-adapter-874e4b1.md "The SuccessFactors (SOAP) sender adapter connects an SAP Cloud Integration tenant to SOAP-based Web Services of a SuccessFactors sender system (synchronous or asynchronous communication).")

[Configure the SuccessFactors SOAP Receiver Adapter](configure-the-successfactors-soap-receiver-adapter-360ef42.md "The SuccessFactors SOAP receiver adapter connects a tenantSAP Cloud Integration to SOAP-based Web services of a SuccessFactors receiver system (synchronous or asynchronous communication).")

[Modifying SuccessFactors SOAP Entity and Operation](modifying-successfactors-soap-entity-and-operation-a6ee603.md "")

