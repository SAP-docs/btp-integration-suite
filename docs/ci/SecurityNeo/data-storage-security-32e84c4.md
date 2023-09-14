<!-- loio32e84c4ae699440fb1b1e79a040519db -->

# Data Storage Security

Customer data can be stored in dedicated steps during message processing.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



Customer data stored at rest is strictly separated and isolated for each tenant. Although different tenants might share a common physical infrastructure, each tenant stores its data in a separate schema.

For certain use cases the customer can configure if the data at rest is encrypted.

Message content can be stored encrypted. If this security measure is configured, the encryption key that is generated automatically is unique for each tenant and is renewed periodically.

Data storage encryption uses AES and a key length of 256 bits. The encryption key is not stored in the same location as the encrypted data.



<a name="loio32e84c4ae699440fb1b1e79a040519db__section_ukv_lxw_vgb"/>

## Kinds of Stored Data

The following kinds of data can be stored during the execution of an integration scenario:

-   Message content

    The runtime node writes message content data to the database in dedicated steps of an integration flow. There is the option to either store message content for a longer time period \(the default is 30 days\) or temporarily. Temporarily stored message content can be used for subsequent message processing steps. Such steps can then also read message content from the database.

    There is the option to configure the retention period of the message content.

-   Monitoring data

    During message processing, the runtime node also writes monitoring data to the database \(which is stored by default for 30 days\). Monitoring data comprises the message processing log \(MPL\), which records the executed processing steps.




## Physical Site

Customer data is stored in various regions worldwide. Here, highest security standards are met. To mention a few examples, redundant power supplies are used and physical access is restricted by means such as biometric access control mechanisms. All of these measures are regularly checked and audited.

More information: [http://www.sapdatacenter.com](http://www.sapdatacenter.com)

All license editions of SAP Cloud Integration include the embedded use of the SAP ASE Platform Edition with a limited disk space.

