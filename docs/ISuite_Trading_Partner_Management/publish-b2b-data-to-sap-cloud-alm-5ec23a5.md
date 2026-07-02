<!-- loio5ec23a5fcfa4454aae3cde8a1b92433d -->

# Publish B2B Data to SAP Cloud ALM

Using SAP Cloud ALM, you can configure alerting based on B2B scenario-specific details, like trading partners or message types.



## Prerequisites

You've connected Trading Partner Management to SAP Cloud ALM to enable monitoring as described in [Setup for SAP Integration Suite \(Trading Partner Management\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-tpm.html).

Note the following constraints:

-   Once the SAP Cloud ALM data collection is enabled for a tenant, it can take up to 12 hours to start publishing the data.
-   Once Trading Partner Management starts publishing data to SAP Cloud ALM, the first publication only involves the latest one-hour data.
-   When new interchanges are created, the publication isn't immediate. Once an interchange is created, it takes about 5 minutes for the data to sync with SAP Cloud ALM.



## Context

SAP Cloud ALM is SAP's central monitoring tool for cloud applications. Trading Partner Management supports publishing B2B interchange data to SAP Cloud ALM for statistics gathering or alerting purposes. For details on enabling and disabling SAP Cloud ALM, see [Setup for SAP Integration Suite \(Trading Partner Management\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-tpm.html) and [SAP Integration Suite \(Trading Partner Management\) - Integration & Exception Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-tpm.html).

To view the business document number on the SAP Cloud ALM dashboard, you need to define a custom search attribute, `document ID`, in Trading Partner Management and assign it to the relevant agreement activity. This process is described in the following.



## Procedure

1.  In SAP Integration Suite, go to *Design* \> *B2B Scenarios* \> *Configuration Manager*.

2.  In the table for custom search attributes, add a new entry by choosing *Create*, and name the new attribute `Document ID`.

3.  Next, add this custom search attribute to your agreement activity.

    1.  Go to *Design* \> *B2B Scenarios* \> *Agreement* and open the relevant agreement.

    2.  In the tab *B2B Scenarios*, go to the tab *Custom Search Attributes* and choose *Add*.

    3.  Select the previously created attribute *Document ID* and maintain the remaining fields. See also [Adding Custom Search Attributes](adding-custom-search-attributes-934bbcd.md).

        > ### Note:  
        > For the IDoc receiver adapter, use the source type *Parameter* and the source value *SAP\_TPM\_IDocNumber*.

    4.  Save your changes.


4.  When the corresponding interchange is published to SAP Cloud ALM, a column called *Document ID* now displays the business document number on the list page of Trading Partner Management messages.

    If no document ID is configured for activities, the *Document ID* column remains empty in SAP Cloud ALM.


