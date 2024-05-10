<!-- loioc36c7c61b310481ebe52c62b3bef3987 -->

# Types of Stored Data

Different kinds of data, such as message content or monitoring data, can be stored during the operation of an B2B scenario.

SAP Trading Partner Management in general deals with configuration for SAP Cloud Integration. Refer to [Data Protection and Privacy](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/0e13ece39471416ebcb9fabc11727793.html) chapter of Cloud Integration to know how the application handles the data.

Such data needs to be considered as sensitive data as it can contain personal information. The following list provides examples:

-   *Trading Partner Profiles including Contact person details*

    Trading Partner profiles allows maintaining the contact person details for different trading partners. This information can be subject to local sensitive data regulations like GDPR. Ensure you handle such data according to the applicable laws. The data is owned, maintained & used by the organization owning the tenant. Apart from providing the infrastructure for maintaining such data, SAP does not have direct access to the data itself.

    The read and write access of the contact person details is protected by appropriate roles. To know more, see [Personas for Trading Partner Management](personas-for-trading-partner-management-d0c9a80.md).

-   *Cloud Integration Runtime Configuration*

    All configurations that are maintained as part of the profiles, agreement templates and the agreement themselves are stored in strictly isolated tenant data bases.

-   *Secure content*

    Secure content that is necessary for the execution of the integrations are stored in the respective secure store of Cloud Integration. This includes user / passwords, private keys, certificates etc. To know more, see [Types of Stored Data](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/183637c9cdcf4a2e8b3dbb602d888e0e.html).

-   *B2B Monitoring content*

    The processed messages, logs and related content is stored in Cloud Integration runtime monitoring as well as in the B2B monitoring storages. Access to sensitive data is restricted with specific authorizations. To know more, see [Types of Stored Data](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/183637c9cdcf4a2e8b3dbb602d888e0e.html).


