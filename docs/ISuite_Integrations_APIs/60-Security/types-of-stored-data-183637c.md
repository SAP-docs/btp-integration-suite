<!-- loio183637c9cdcf4a2e8b3dbb602d888e0e -->

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



Customer data stored at rest is strictly separated and isolated for each tenant. Although different tenants might share a common physical infrastructure, each tenant stores its data in a separate schema.

For certain use cases the customer can configure if the data at rest is encrypted.

Message content can be stored encrypted. If this security measure is configured, the encryption key that is generated automatically is unique for each tenant and is renewed periodically.

Data storage encryption uses AES and a key length of 256 bits. The encryption key is not stored in the same location as the encrypted data.



<a name="loio183637c9cdcf4a2e8b3dbb602d888e0e__section_nfl_ryf_vyb"/>

## Using Edge Integration Cell

Customer data can be stored by dedicated steps during message processing. Edge Integration Cell stores data in the edge environment using persistent volumes. Amazon Web Services \(AWS\) and Microsoft Azure support data encryption at rest. For more information, check the documentation of the related platform.

