<!-- loio7a4fe7d85e10416e9dd63f98ccd780b2 -->

# Anomaly Detection

Anomaly detection is an AI-based feature that involves the identification of patterns or data points that deviate significantly from normal behavior or expected patterns. This feature allows you to proactively identify and respond to unusual patterns or deviations in API proxy calls, thereby ensuring the security, reliability, and optimal performance of APIs.

> ### Note:  
> The availability of the anomaly detection and prediction features depends on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://me.sap.com/notes/2903776) and [3463620](https://me.sap.com/notes/3463620).



<a name="loio7a4fe7d85e10416e9dd63f98ccd780b2__section_vfx_qly_s1c"/>

## How it works

Anomaly detection involves training an AI model to understand the behavior of your API proxies \(“proxified” API endpoints\). It works by comparing a current timeframe \(referred to as a 'window'\) of API proxy calls with the corresponding past time-series data. The AI model will be trained automatically using all past API data that is available, with a minimum requirement of 3 months' worth of data. Therefore, it is necessary to have at least 3 months' worth of API data on an API proxy to train the model and reliably detect anomalies. The detection capability improves over time.

On average, the training process takes approximately 3 hours to complete.

Anomaly detection is currently offered for the following behaviors:

-   API Traffic \(API Call Count\)

-   Latency \(Total Response Time\)
-   API Error Count \(4XX and 5XX Error Count\)

Once activated, the anomaly detection feature automatically collects a time series of the aggregate set of API proxy calls in the tenant that have a sufficient amount of past API call data. This enables it to identify anomalies in the aggregate set of all configured API proxies.

In addition, you can select up to five individual APIs, and track call behavior for these APIs. For instance, you may be interested in tracking client errors to a specific, sensitive API, in addition to the number of errors in total for the tenant.



<a name="loio7a4fe7d85e10416e9dd63f98ccd780b2__section_k2y_pzp_31c"/>

## Benefits

-   **Active Monitoring**: Enables active monitoring by highlighting potential anomalies, helping address the issues promptly.
-   **Identification of Irregularities**: Visualizing the data enables quick identification of irregularities or patterns that deviate from normal behavior.
-   **Notification Alerts**: You now have the option to subscribe to the **SAP Alert Notification Service** and start receiving alerts whenever an anomaly is detected through your preferred communication channel. This enables immediate action, minimizing the potential impact of the anomaly and ensuring timely resolution of any issues. For more information, see [Subscribing to Notification Alerts](subscribing-to-notification-alerts-88e96f4.md).

