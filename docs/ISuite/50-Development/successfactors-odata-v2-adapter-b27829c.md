<!-- loiob27829c720db4773a147b8bb2b61c2ba -->

# SuccessFactors OData V2 Adapter

The SuccessFactors adapter enables you to communicate with the SuccessFactors system. You use the OData V2 message protocol to connect to the OData V2 Web services of the SuccessFactors system.

The OData V2 message protocol for the SuccessFactors adapter is available only in the receiver channel. For more information, see [Configure the SuccessFactors OData V2 Receiver Adapter](configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md).

> ### Tip:  
> -   If your input payload contains nodes without data, the output will also contain empty strings. If you want to avoid empty strings in the output, ensure that the input payload does not contain any empty nodes.
> -   You can use headers and exchange properties in the adapter settings to dynamically pass values at runtime. For more information, see [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md).

Whenever the SuccessFactors OData V2 adapter is used, the following headers with the specified values will be sent to the SuccessFactors back end as HTTP request headers:

1.  X-SF-Correlation-Id : MPL ID

2.  X-SF-Client-Tenant-Id : Client/Tenant ID

3.  X-SF-Process-Name : iFlow Name

4.  X-Agent-Name : SAP Cloud Integration


**Related Information**  


[Configure the SuccessFactors OData V2 Receiver Adapter](configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md "Configure the SuccessFactors OData V2 receiver adapter by understanding the adapter parameters.")

