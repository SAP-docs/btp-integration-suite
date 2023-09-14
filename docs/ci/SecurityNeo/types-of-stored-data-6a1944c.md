<!-- loio6a1944c59c0f4aceab3707b8d8993e3d -->

# Types of Stored Data

Different kinds of data, such as message content or monitoring data, can be stored during the operation of an integration scenario.



Such data needs to be considered as sensitive data as it can contain personal information. The following list provides examples:

-   Message content

    Messages processed on a runtime node typically contain business data of an integration scenario and therefore can contain sensitive customer data such as addresses, names, or financial information.

    When this data is *at-rest*, it can be stored encrypted. Note, however, that in some use cases the customer can configure that the data is not encrypted.

    When this data is *in-transit*, several measures can be taken, such as digital message signing or message content encryption.

-   Monitoring data

    The message processing log records the processing steps of an integration flow. Only users assigned to this tenant and with dedicated permissions can access this data.

-   Other data, such as the content of log files


> ### Note:  
> Personal data processed by and stored on the integration platform is handled according to the Data Processing Agreement, which you can find at [http://www.sap.com/about/agreements.html](http://www.sap.com/about/agreements.html) under *SAP Cloud Services Customers*.

Due to the tenant isolation concept, data from different customers \(stored in different tenants\) is strictly isolated. Additionally, SAP has no access to data stored in customer tenants.

The customer can grant people outside its organization permissions to execute specific tasks on its cluster \(for example, to SAP employees to execute error analysis tasks in support cases\).

**Related Information**  


[Specific Data Assets](specific-data-assets-f922344.md "Different kinds of data are stored in the SAP Cloud Integration infrastructure during the lifecycle of an integration project.")

