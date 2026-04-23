<!-- loio9e7e5d184ade485d9e19c1c4bede2c6f -->

# Configuring APIs for Anomaly Detection

View or configure APIs for anomaly detection.



<a name="loio9e7e5d184ade485d9e19c1c4bede2c6f__context_wtf_rbv_21c"/>

## Context

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through June 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

The Anomaly Detection feature can monitor API behavior both at the tenant level and for individual API proxies. Monitoring individual APIs allows you to detect unusual traffic patterns, latency changes, or error spikes for specific APIs.

Before you can monitor individual APIs, you must enable them for anomaly detection.

Only API proxies that meet the required historical data prerequisites are available for selection. These prerequisites ensure that sufficient historical data exists to train the anomaly detection model. For more information about these requirements, see [Prerequisites for API Selection](anomaly-detection-7a4fe7d.md#loio7a4fe7d85e10416e9dd63f98ccd780b2__section_qp4_nms_p3c) section in the [Anomaly Detection](anomaly-detection-7a4fe7d.md) topic.

To view or modify the APIs for anomaly detection, follow the steps below:



## Procedure

1.  Log on to the **SAP Integration Suite**.

2.  Choose *Settings* \> *Artificial Intelligence* from the left navigation pane.

3.  If the **Anomaly Detection** feature is not activated, then locate it and switch the toggle button to the *ON* position.

    > ### Note:  
    > The **Predictions** feature is associated with Anomaly Detection and becomes active when the toggle button is set to the *ON* position.

    Once the feature is activated, the **Anomaly Detection** section displays the top 5 APIs currently being monitored, which have received the highest traffic over the past 6 months.

4.  To modify the list of pre-selected APIs, choose *Modify*.

5.  Check or uncheck the desired APIs, and then choose *Modify* in the *Modify APIs* dialog.

    The *Modify APIs* dialog displays the list of API proxies that meet the minimum historical data requirements for anomaly detection.

    > ### Note:  
    > Currently, you can select up to 50 individual APIs for anomaly detection.

    > ### Note:  
    > If an API proxy does not meet the minimum historical data prerequisites, it will not appear in the API selection list in the *Modify APIs* dialog.

6.  Choose *Confirm* to save your changes.

    The selected APIs are now enabled for anomaly detection.

    > ### Note:  
    > Each time you modify the configuration, the AI model needs to be retrained to effectively detect anomalies. On average, the training process takes approximately four hours to complete. Therefore, it is not recommended to make frequent configuration changes.




## Results

After enabling APIs for anomaly detection, the system begins monitoring the selected API proxies and analyzing their traffic patterns. The anomaly detection model uses historical API call data to identify deviations from expected behavior.

**Related Information**  


[Enabling Anomaly Detection, Intelligent Recommendations, and API Call Predictions](enabling-anomaly-detection-intelligent-recommendations-and-api-call-predictions-98534a0.md "Activate anomaly detection, intelligent recommendations, and API call prediction to enhance monitoring and forecasting capabilities for API calls.")

[Working with Detected Anomalies](working-with-detected-anomalies-1c677b2.md "Access and analyze anomalies in the analytics dashboard. Discover details about the various types of anomalies, evaluate and resolve them.")

[Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md "Receive real-time alerts for anomaly detection services, delivered to your preferred communication channel.")

