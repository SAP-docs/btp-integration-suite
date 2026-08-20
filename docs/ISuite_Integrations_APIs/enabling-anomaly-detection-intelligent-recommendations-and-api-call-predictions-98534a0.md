<!-- loio98534a0f8d1d4c4d98bea4b84e762787 -->

# Enabling Anomaly Detection, Intelligent Recommendations, and API Call Predictions

Activate **Anomaly Detection**, **Intelligent Recommendations**, and **API Call Predictions** to enhance monitoring and forecasting capabilities for API calls.



<a name="loio98534a0f8d1d4c4d98bea4b84e762787__prereq_pkk_gsy_31c"/>

## Prerequisites

The role collection *APIPortal.Administrator* must be assigned to you.

To enable Intelligent Recommendations, the role collection *APIManagement.SelfService.Administrator* must be assigned to you.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).



<a name="loio98534a0f8d1d4c4d98bea4b84e762787__context_ncd_4rs_21c"/>

## Context

To enable Anomaly Detection, Intelligent Recommendations, and API Call Predictions in SAP Integration Suite, perform the following steps:



## Procedure

1.  Log on to **SAP Integration Suite**.

2.  From the left navigation pane, choose *Settings* \> *Artificial Intelligence*.

3.  Locate the following AI features in the features list and toggle *Activation Status* to *ON*:

    -   Anomaly Detection
    -   API Call Predictions

        > ### Note:  
        > A single toggle button controls both the Anomaly Detection and Prediction features simultaneously.


4.  \(Optional\) Enable Intelligent Recommendations:

    1.  Under *Anomaly Detection*, select the *Intelligent Recommendations* checkbox.

    2.  Review and accept the terms and conditions in the dialog that appears.


    > ### Note:  
    > For details on data retention and reactivation behavior when the feature is disabled, see  <?sap-ot O2O class="- topic/xref " href="1d6756e093da4bd0882eb6e34ff8cb0e.xml" text="" desc="" xtrc="xref:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/98534a0f8d1d4c4d98bea4b84e762787.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .




<a name="loio98534a0f8d1d4c4d98bea4b84e762787__result_jpj_rrs_21c"/>

## Results

The selected AI features are enabled. Anomaly Detection begins monitoring API traffic, and predictions are generated based on historical data patterns.

**Related Information**  


[Configuring APIs for Anomaly Detection](configuring-apis-for-anomaly-detection-9e7e5d1.md "View or configure APIs for anomaly detection.")

[Working with Detected Anomalies](working-with-detected-anomalies-1c677b2.md "Access and analyze anomalies in the analytics dashboard. Discover details about the various types of anomalies, evaluate and resolve them.")

[Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md "Receive real-time alerts for anomaly detection services, delivered to your preferred communication channel.")

