<!-- loio98534a0f8d1d4c4d98bea4b84e762787 -->

# Enabling Anomaly Detection, Intelligent Recommendations, and API Call Predictions

Activate anomaly detection, intelligent recommendations, and API call prediction to enhance monitoring and forecasting capabilities for API calls.



<a name="loio98534a0f8d1d4c4d98bea4b84e762787__prereq_pkk_gsy_31c"/>

## Prerequisites

The role collection *APIPortal.Administrator* must be assigned to you.

The role collection *APIManagement.SelfService.Administrator* must be assigned to you to enable intelligent recommendations.

> ### Note:  
> The availability of the anomaly detection and prediction features depends on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://me.sap.com/notes/2903776) and [3463620](https://me.sap.com/notes/3463620).



<a name="loio98534a0f8d1d4c4d98bea4b84e762787__context_ncd_4rs_21c"/>

## Context

To enable anomaly detection and API call prediction through the SAP Integration Suite, follow the steps below:



## Procedure

1.  Log on to the **SAP Integration Suite**.

2.  Choose *Settings* \> *Artificial Intelligence* from the left navigation pane.

3.  Locate the following AI features and switch the toggle button to the *ON* position:

    -   Anomaly Detection
    -   API Call Prediction

        > ### Note:  
        > A single toggle button controls both the anomaly detection and prediction features simultaneously.


    > ### Caution:  
    > Disabling the anomaly detection feature will delete all associated anomaly data.

4.  \(Optional\) Under anomaly detection, select the checkbox *Intelligent Recommendations* and accept the terms and conditions to enable the feature.

    > ### Note:  
    > Intelligent recommendations provides detailed observations of detected anomalies, including likely causes and recommended actions to resolve issues. The activation or deactivation of this feature has no impact on anomaly detection or API call prediction.




<a name="loio98534a0f8d1d4c4d98bea4b84e762787__result_jpj_rrs_21c"/>

## Results

Anomaly detection, API call prediction, and intelligent recommendations are now enabled.

**Related Information**  


[Configuring APIs for Anomaly Detection](configuring-apis-for-anomaly-detection-9e7e5d1.md "View or configure APIs for anomaly detection.")

[Working with Detected Anomalies](working-with-detected-anomalies-1c677b2.md "Access and analyze anomalies in the analytics dashboard. Discover details about the various types of anomalies, evaluate and resolve them.")

[Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md "Receive real-time alerts for anomaly detection services, delivered to your preferred communication channel.")

