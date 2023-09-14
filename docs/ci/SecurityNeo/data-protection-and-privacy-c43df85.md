<!-- loioc43df85c454f4da18dc80c17d512be33 -->

# Data Protection and Privacy

Various types of customer data are processed by and stored on the integration platform at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.



<a name="loioc43df85c454f4da18dc80c17d512be33__section_zxg_cyw_vgb"/>

## General Information

Governments place legal requirements on industry to protect data and privacy. We provide features and functions to help you meet these requirements.

> ### Caution:  
> SAP does not provide legal advice in any form. SAP software supports data protection compliance by providing security features and data protection-relevant functions, such as blocking and deletion of personal data. In many cases, compliance with applicable data protection and privacy laws is not covered by a product feature. Furthermore, this information should not be taken as advice or a recommendation regarding additional features that would be required in specific IT environments. Decisions related to data protection must be made on a case-by-case basis, taking into consideration the given system landscape and the applicable legal requirements. Definitions and other terms used in this documentation are not taken from a specific legal source.

> ### Caution:  
> We assume that you have not maintained any data related to an individual in the tools provided by SAP Cloud Integration \(for example, when designing integration content\).
> 
> We expect that sensitive personal data can only be included in message payloads. This responsibility lies exclusively with you as the operator of an integration scenario using SAP Cloud Integration and remains your responsibility. If you include sensitive personal data within payloads or message attachments, SAP Cloud Integration may store this information on your behalf. This applies also for data maintained in the tools provided by SAP Cloud Integration, however, data within payloads can be protected by enabling encrypted storage.
> 
> The knowledge of sensitive personal data lies exclusively with you and remains your responsibility.
> 
> The tools of SAP Cloud Integration only use technical users or data without any references to individuals.



<a name="loioc43df85c454f4da18dc80c17d512be33__section_jq4_3yw_vgb"/>

## User Consent

We assume that software operators, such as SAP customers, collect and store the consent of data subjects, before collecting their personal data. A data privacy specialist can later determine whether data subjects have granted, withdrawn, or denied consent.



<a name="loioc43df85c454f4da18dc80c17d512be33__section_ovk_hfj_ycb"/>

## Read Access Logging

Read Access Logging is used to monitor and log read access to sensitive data. Data may be categorized as sensitive by law, by external company policy, or by internal company policy. Read Access Logging enables you to answer questions about who accessed particular data within a specified time frame. Such questions could be:

-   Who accessed the data of a given business entity, for example, a bank account?

-   Who accessed personal information, such as health data?

-   Who accessed personal data of accounts or business partners?


A tenant administrator can display audit logs for a tenant using the Monitoring application of the Web UI \(under *Manage Security* in the *Audit Log* tile\).

Additionally, within SAP, audit logs can be displayed for teams in charge of maintaining the virtual cloud environment and to analyze and resolve error situations. Audit logs related to different customers are separated from each other \(according to the tenant isolation feature\).

More information: [Security-Relevant Logging and Tracing](security-relevant-logging-and-tracing-d4c6d94.md)



<a name="loioc43df85c454f4da18dc80c17d512be33__section_gk4_qfj_ycb"/>

## Information Report

An information report is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a report or an application may offer a self-service. SAP Cloud Integration assumes that software operators, such as SAP customers, can provide such information.



<a name="loioc43df85c454f4da18dc80c17d512be33__section_xqc_tfj_ycb"/>

## Erasure of Personal Data

When handling personal data, consider the legislation in the different countries where your organization operates. After the data has passed the end of purpose, regulations may require you to delete the data. However, additional regulations may require you to keep the data longer. During this period you must block access to the data by unauthorized persons until the end of the retention period, when the data is finally deleted.

Data stored on the SAP Cloud Integration tenant is only stored for a limited time period \(referred to as retention time\).

For more information on the retention times for the various kinds of data stored by SAP Cloud Integration, see [Specific Data Assets](specific-data-assets-f922344.md).

**Related Information**  


[Types of Stored Data](types-of-stored-data-6a1944c.md "Different kinds of data, such as message content or monitoring data, can be stored during the operation of an integration scenario.")

[Specific Data Assets](specific-data-assets-f922344.md "Different kinds of data are stored in the SAP Cloud Integration infrastructure during the lifecycle of an integration project.")

[Security-Relevant Logging and Tracing](security-relevant-logging-and-tracing-d4c6d94.md "Audit logs allow administrators at SAP or the tenant administrator to monitor events such as data read accesses or system configuration changes. This enables administrators to take adequate measures to prevent malicious usage of the system.")

[Data Storage Security](data-storage-security-32e84c4.md "Customer data can be stored in dedicated steps during message processing.")

