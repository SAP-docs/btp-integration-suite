<!-- loioba211bee152048bcb457723990355cc0 -->

# Create Custom Dimensions and Measures

Capture and analyze data using custom dimensions and custom measures.



## Context

Advanced API Analytics provides a set of default dimensions and measures to track analytics data. However, if you need dimensions and measures that aren't included in the default list, you can create custom dimensions and measures.

With a custom dimension or a custom measure, you collect and analyze data that analytics don't automatically track. For instance, you want to capture API calls or API errors based on an API Key. Advanced API Analytics doesn't provide an out-of-the-box dimension that allows you to track data based on an API key. In such cases, you can define a custom dimension for capturing API-Key-based data. Similarly, you want to track the number of headers passed in an API call. In such cases, you can create a custom measure to track the total or average number of headers passed in an API call.

> ### Note:  
> The recommended maximum size for values of custom metrics and dimensions is 1,000 characters. Values that exceed 5,000 characters are automatically truncated after 5,000 characters.

Perform the step-by-step instructions in this topic to create custom dimensions and measures.



## Procedure

1.  In the analytics dashboard, choose *Create* to open the Create Chart dialog.

2.  In the Dimensions and Measures section, select the dimension or measure you want to use for tracking data. Custom dimensions and measures that are enabled through the Statistics Collector policy of your API proxy appear in these dropdown lists and can be used while creating charts. This procedure is explained in further steps.

3.  Enter the required chart details and choose *Save*.

4.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

5.  From the APIs list, choose the required API for which you want to collect data using the custom metric.

6.  Choose *Policies* \> *Edit*.

7.  Attach the [Statistics Collector Policy](statistics-collector-policy-1dee3c9.md) to the PreFlow of your ProxyEndpoint. For more information about how to add policies to API proxy, see [Policies](policies-7e4f3e5.md).

8.  Open the payload of Statistics Collector policy that you attached to the API proxy.

    > ### Note:  
    > By default, the payload of Statistics Collector policy displays all the custom dimensions and measures that you've created. It displays them in a commented state with xml indicators `<!-- -->` as shown in the below sample payload:

    > ### Sample Code:  
    > ```
    > <!-- The policy collects data for each request and passes to the analytics server. In the below sample payload, you can see a custom dimension 'APIKey' for 
    >              collecting data based on API keys and a custom measure 'HeadersCount' for collecting the count of API headers passed in API calls. -->
    > 
    > <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    > <StatisticsCollector xmlns="http://www.sap.com/apimgmt">
    >     <Statistics>
    >         <!-- <Statistic name="APIKey" ref="request.header.APIKey" type="string">999999</Statistic> -->
    >         <!-- <Statistic name="HeadersCount" ref="request.headers.count" type="integer">0</Statistic> -->
    >     </Statistics>
    > </StatisticsCollector>
    > ```

    To enable data collection, you must uncomment the custom dimension or the measure with which you want to enable data tracking. In the below sample payload, data collection is enabled only for the custom dimension `APIKey`.

    > ### Sample Code:  
    > ```
    > 
    > <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    > <StatisticsCollector xmlns="http://www.sap.com/apimgmt">
    >     <Statistics>
    >         <Statistic name="APIKey" ref="request.header.APIKey" type="string">999999</Statistic>
    >         <!-- <Statistic name="HeadersCount" ref="request.headers.count" type="integer">0</Statistic> -->
    >     </Statistics>
    > </StatisticsCollector>
    > ```

9.  After enabling the custom dimension or measure in the Statistics Collector policy, navigate to the analytics dashboard and use Create to build charts using these dimensions or measures.

    > ### Note:  
    > After creating a chart with custom dimension or custom measure, you'll experience a delay of 20-30 minutes before data starts appearing in the charts.

    > ### Remember:  
    > You can't recreate a custom metric with the same name once you have deleted it.


**Related Information**  


[Advanced API Analytics](advanced-api-analytics-5973d4a.md "Advanced API Analytics brings to you the all new analytics dashboard, providing handy and powerful analytical reporting tools to track your API performance and usage.")

[Create and Work with Custom Reports](create-and-work-with-custom-reports-daf54fd.md "Create your own custom reports in Advanced API Analytics dashboard.")

