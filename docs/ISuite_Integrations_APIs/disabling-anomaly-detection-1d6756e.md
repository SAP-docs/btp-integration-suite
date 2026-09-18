<!-- loio1d6756e093da4bd0882eb6e34ff8cb0e -->

# Disabling Anomaly Detection

Deactivate the Anomaly Detection feature and understand its impact on associated data.



## Prerequisites

The role collection *APIPortal.Administrator* must be assigned to you.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).



## Context

Disabling Anomaly Detection stops monitoring and forecasting activities for API calls. Since a single toggle controls both Anomaly Detection and API Call Predictions, disabling one deactivates the other. Follow the steps below to disable the feature.



## Procedure

1.  Log on to **SAP Integration Suite**.

2.  From the left navigation pane, choose *Settings* \> *Artificial Intelligence*.

3.  Locate the following AI features in the features list and toggle *Activation Status* to *OFF*:

    -   Anomaly Detection
    -   API Call Predictions

    > ### Note:  
    > When the Anomaly Detection feature is disabled, associated data is retained for**7 days** and permanently deleted thereafter. Reactivating the feature within this 7-day window restores full functionality with all previous data preserved.




## Results

**Anomaly Detection** and **API Call Predictions** are deactivated. Monitoring and forecasting activities are stopped, and associated data enters the 7-day retention period before permanent deletion.

