<!-- loio9e7e5d184ade485d9e19c1c4bede2c6f -->

# Configuring APIs for Anomaly Detection

View or configure APIs for anomaly detection.



<a name="loio9e7e5d184ade485d9e19c1c4bede2c6f__context_wtf_rbv_21c"/>

## Context

> ### Note:  
> The availability of the anomaly detection feature is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://me.sap.com/notes/2903776) and [3463620](https://me.sap.com/notes/3463620).

To view or modify the APIs for anomaly detection, follow the steps below:



## Procedure

1.  Log on to the SAP Integration Suite.

2.  Click on the navigation icon on the left and select *Settings* \> *APIs*.

3.  Go to the *Anomaly Detection* tab.

4.  If anomaly detection is not already enabled, switch the radio button to the *ON* position. This will display the **API Selection** section.

5.  In the **API Selection** section, when you enable anomaly detection for the first time, by default, the system will automatically select and display the top 5 APIs that have received the highest amount of traffic in the past 6 months.

6.  To make changes to the selection of APIs, click *Modify*.

7.  The *Modify APIs* window displays a list of APIs that meet the minimum data requirement \(at least 3 months\) and are available for training. Currently, you can select up to five individual APIs for anomaly detection. Use the checkboxes to select or deselect the desired APIs, and then click on *Modify*.

8.  In the dialog box that appears, click on *Confirm* to save your changes.

    > ### Note:  
    > Each time you modify the configuration, the AI model needs to be retrained to effectively detect anomalies. On average, the training process takes approximately 3 hours to complete. Therefore, it is not recommended to make frequent configuration changes.


**Related Information**  


[Enabling Anomaly Detection](enabling-anomaly-detection-98534a0.md "To detect anomalies for API proxy calls, you need to enable the anomaly detection setting.")

[Working with Detected Anomalies](working-with-detected-anomalies-1c677b2.md "Access and analyze anomalies in the analytics dashboard. Discover details about the various types of anomalies, evaluate and resolve them.")

[Subscribing to Email Notification Alerts](subscribing-to-email-notification-alerts-88e96f4.md "Receive real-time email alerts for anomaly detection services.")

