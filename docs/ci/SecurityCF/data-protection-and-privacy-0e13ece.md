<!-- loio0e13ece39471416ebcb9fabc11727793 -->

# Data Protection and Privacy

Various types of customer data are processed by and stored on the integration platform at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.



<a name="loio0e13ece39471416ebcb9fabc11727793__section_zxg_cyw_vgb"/>

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



<a name="loio0e13ece39471416ebcb9fabc11727793__section_jq4_3yw_vgb"/>

## User Consent

We assume that software operators, such as SAP customers, collect and store the consent of data subjects, before collecting their personal data. A data privacy specialist can later determine whether data subjects have granted, withdrawn, or denied consent.



<a name="loio0e13ece39471416ebcb9fabc11727793__section_gk4_qfj_ycb"/>

## Information Report

An information report is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a report or an application may offer a self-service. Cloud Integration assumes that software operators, such as SAP customers, can provide such information.



<a name="loio0e13ece39471416ebcb9fabc11727793__section_xqc_tfj_ycb"/>

## Erasure of Personal Data

When handling personal data, consider the legislation in the different countries where your organization operates. After the data has passed the end of purpose, regulations may require you to delete the data. However, additional regulations may require you to keep the data longer. During this period you must block access to the data by unauthorized persons until the end of the retention period, when the data is finally deleted.

Data stored on Cloud Integration is only stored for a limited time period \(referred to as retention time\).

For more information on the retention times for the various kinds of data stored by Cloud Integration, see [Specific Data Assets](specific-data-assets-0e4e511.md).

