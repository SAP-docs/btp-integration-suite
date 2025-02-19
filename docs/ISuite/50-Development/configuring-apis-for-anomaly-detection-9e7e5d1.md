<!-- loio9e7e5d184ade485d9e19c1c4bede2c6f -->

# Configuring APIs for Anomaly Detection

View or configure APIs for anomaly detection.



<a name="loio9e7e5d184ade485d9e19c1c4bede2c6f__context_wtf_rbv_21c"/>

## Context

> ### Note:  
> The availability of the anomaly detection and prediction features depends on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://me.sap.com/notes/2903776) and [3463620](https://me.sap.com/notes/3463620).

To view or modify the APIs for anomaly detection, follow the steps below:



## Procedure

1.  Log on to the **SAP Integration Suite**.

2.  From the left navigation pane, choose *Settings* \> *APIs*.

3.  Go to the *Analyze* tab.

4.  Toggle the radio button to the *ON* position if anomaly detection is not already enabled.

    Under *API Selection*, you will see the top 5 APIs that have received the highest amount of traffic in the past 6 months.

5.  To modify the list of preselected APIs, choose *Modify*.

6.  Check or uncheck the desired APIs, and then choose *Modify* in the **Modify APIs** dialog.

    The *Modify APIs* dialog will display the list of APIs that meet the minimum data requirement \(at least 3 months' worth of API data\) and are available for AI model training.

    > ### Note:  
    > Currently, you can select up to five individual APIs for anomaly detection.

7.  Choose *Confirm* to save your changes.

    > ### Note:  
    > Each time you modify the configuration, the AI model needs to be retrained to effectively detect anomalies. On average, the training process takes approximately 3 hours to complete. Therefore, it is not recommended to make frequent configuration changes.


**Related Information**  


[Enabling Anomaly Detection and Predictions](enabling-anomaly-detection-and-predictions-98534a0.md "Activate the anomaly detection and prediction features for API proxy calls to enhance monitoring and forecasting capabilities.")

[Working with Detected Anomalies](working-with-detected-anomalies-1c677b2.md "Access and analyze anomalies in the analytics dashboard. Discover details about the various types of anomalies, evaluate and resolve them.")

[Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md "Receive real-time alerts for anomaly detection services, delivered to your preferred communication channel.")

