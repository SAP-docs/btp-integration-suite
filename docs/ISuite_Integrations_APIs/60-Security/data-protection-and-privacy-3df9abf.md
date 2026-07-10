<!-- loio3df9abfb203c47acbd0cfee39a959d9f -->

# Data Protection and Privacy



<a name="loio3df9abfb203c47acbd0cfee39a959d9f__SecurityGuideDPP1"/>

## General Information

Governments place legal requirements on industry to protect data and privacy. We provide features and functions to help you meet these requirements.

> ### Caution:  
> SAP does not provide legal advice in any form. SAP software supports data protection compliance by providing security features and data protection-relevant functions, such as blocking and deletion of personal data. In many cases, compliance with applicable data protection and privacy laws is not covered by a product feature. Furthermore, this information should not be taken as advice or a recommendation regarding additional features that would be required in specific IT environments. Decisions related to data protection must be made on a case-by-case basis, taking into consideration the given system landscape and the applicable legal requirements. Definitions and other terms used in this documentation are not taken from a specific legal source.

> ### Caution:  
> We assume that you have not maintained any data related to an individual in the tools provided by SAP Integration Suite \(for example, when designing integration content\).
> 
> We expect that sensitive personal data can only be included in message payloads. This responsibility lies exclusively with you as the operator of an integration scenario using SAP Integration Suite and remains your responsibility. If you include sensitive personal data within payloads or message attachments, SAP Integration Suite may store this information on your behalf. This applies also for data maintained in the tools provided by SAP Integration Suite, however, data within payloads can be protected by enabling encrypted storage.
> 
> The knowledge of sensitive personal data lies exclusively with you and remains your responsibility.
> 
> The tools of SAP Integration Suite only use technical users or data without any references to individuals.



<a name="loio3df9abfb203c47acbd0cfee39a959d9f__SecurityGuideDPPUserConsent"/>

## User Consent

We assume that software operators, such as SAP customers, collect and store the consent of data subjects, before collecting their personal data. A data privacy specialist can later determine whether data subjects have granted, withdrawn, or denied consent.



<a name="loio3df9abfb203c47acbd0cfee39a959d9f__section_gk4_qfj_ycb"/>

## Information Report

An information report is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a report or an application may offer a self-service. SAP Integration Suite assumes that software operators, such as SAP customers, can provide such information.



<a name="loio3df9abfb203c47acbd0cfee39a959d9f__section_xqc_tfj_ycb"/>

## Erasure of Personal Data

When handling personal data, consider the legislation in the different countries where your organization operates. After the data has passed the end of purpose, regulations may require you to delete the data. However, additional regulations may require you to keep the data longer. During this period you must block access to the data by unauthorized persons until the end of the retention period, when the data is finally deleted.

Data stored by SAP Integration Suite is only stored for a limited time period \(referred to as retention time\).

For more information on the retention times for the various kinds of data stored by SAP Integration Suite \(grouped by capability\), see:

-   [Kinds of Stored Data](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/cfb9ffbb3df24f7e9ff9d25280767e6a.html "Integration Assessment stores SAP Integration Solution Advisory Methodology (ISA-M) master data predefined by SAP, ISA-M master data adapted by customers, and data associated with business solution requests and interface requests.") :arrow_upper_right: \(for Integration Assessment\)

-   [Types of Stored Data](types-of-stored-data-183637c.md) and [Specific Data Assets](specific-data-assets-0e4e511.md) \(for Cloud Integration\)

-   [Specific Data Assets](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/a6491d23d2444d7384f8e11f7134bceb.html "") :arrow_upper_right: \(for Integration Advisor\)

-   [Types of Stored Data](https://help.sap.com/viewer/4ca9c92a6c1641aea939927aa2b37f1b/CLOUD/en-US/c36c7c61b310481ebe52c62b3bef3987.html "Different kinds of data, such as message content or monitoring data, can be stored during the operation of an B2B scenario.") :arrow_upper_right: and [Specific Data Assets](https://help.sap.com/viewer/4ca9c92a6c1641aea939927aa2b37f1b/CLOUD/en-US/16077ced3bb7414db563e2e97b9d07a4.html "") :arrow_upper_right: \(for Trading Partner Management\)


**Related Information**  


[Data Protection and Privacy for Integration Assessment](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/9ef9fbc1e6b04ee09cc0491ff493d1a9.html "") :arrow_upper_right:

[Data Protection and Privacy for API Management](data-protection-and-privacy-for-api-management-d50613e.md "")

[Data Protection and Privacy for Cloud Integration](data-protection-and-privacy-for-cloud-integration-0e13ece.md "Various types of customer data are processed by and stored on the integration platform at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.")

[Data Protection and Privacy for Integration Advisor](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/b1b36277f6c24eeb88824463a1f4dac3.html "") :arrow_upper_right:

[Data Protection and Privacy for Trading Partner Management](https://help.sap.com/viewer/4ca9c92a6c1641aea939927aa2b37f1b/CLOUD/en-US/ca3bb434c2ab417382a15276425d2798.html "Various types of customer data are processed by and stored on the integration platform at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.") :arrow_upper_right:

