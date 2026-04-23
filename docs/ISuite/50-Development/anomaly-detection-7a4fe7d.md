<!-- loio7a4fe7d85e10416e9dd63f98ccd780b2 -->

# Anomaly Detection

Anomaly detection is an AI-based feature that involves the identification of patterns or data points that deviate significantly from normal behavior or expected patterns. This feature allows you to proactively identify and respond to unusual patterns or deviations in API traffic, thereby ensuring the security, reliability, and optimal performance of APIs.



<a name="loio7a4fe7d85e10416e9dd63f98ccd780b2__section_vfx_qly_s1c"/>

## How it works

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through June 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

Anomaly detection involves training an AI model to understand the behavior of your API calls. It works by comparing a current time frame \(referred to as a 'window'\) of API calls with the corresponding historical time-series data. The AI model is trained automatically using all available historical API data, with a minimum requirement of three months of historical API data. The historical data must also meet the required volume threshold to enable reliable model training. For more information, see [Prerequisites for API Selection](anomaly-detection-7a4fe7d.md#loio7a4fe7d85e10416e9dd63f98ccd780b2__section_qp4_nms_p3c).

On average, the training process takes approximately **four hours** to complete.

Anomaly detection is currently offered for the following behaviors:

-   API Traffic \(API Call Count\)

-   Latency \(Total Response Time\)
-   API Error Count \(4XX and 5XX Error Count\)

Once activated, the anomaly detection feature automatically collects a time series of the aggregate set of API calls in the tenant that have sufficient historical API call data. This enables it to identify anomalies in the overall traffic across all configured APIs.

In addition, you can select up to fifty \(50\) individual APIs and track their call behavior. Only API proxies that meet the required historical data prerequisites are available for selection. For example, you might want to monitor client errors for a specific sensitive API, in addition to tracking the total number of errors across the tenant.



<a name="loio7a4fe7d85e10416e9dd63f98ccd780b2__section_qp4_nms_p3c"/>

## Prerequisites for API Selection

To use the Anomaly Detection feature for individual APIs, the API proxies must meet the following prerequisites to be listed in the API selection list in the *Modify APIs* dialog:

-   **Minimum API aging period:** The API must have at least three months of historical usage data. During this period, API call activity is recorded at **30-minute** intervals.

-   **Minimum historical data threshold:** The API must accumulate at least **4,320** data points. This corresponds to the minimum historical dataset required for the AI model to learn normal API usage patterns.

    The historical data enables the anomaly detection model to identify patterns such as usage trends and seasonality, thereby improving the accuracy of anomaly detection.

    Once these conditions are met, the corresponding API proxies become available for selection.


> ### Note:  
> APIs that do not meet the minimum aging period or required historical data threshold are not listed in the API selection list in the *Modify APIs* dialog.



<a name="loio7a4fe7d85e10416e9dd63f98ccd780b2__section_k2y_pzp_31c"/>

## Benefits

-   **Active Monitoring**: Enables active monitoring by highlighting potential anomalies, helping address the issues promptly.
-   **Identification of Irregularities**: Visualizing the data enables quick identification of irregularities or patterns that deviate from normal behavior.
-   **Notification Alerts**: You now have the option to subscribe to the **SAP Alert Notification Service** and start receiving alerts whenever an anomaly is detected through your preferred communication channel. This enables immediate action, minimizing the potential impact of the anomaly and ensuring timely resolution of any issues. For more information, see [Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md).

