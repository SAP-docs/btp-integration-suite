<!-- loioe9617dd737384100b96194d37badbb80 -->

# Inspect System Memory Usage

Inspect usage of the system memory for a given time period \(as selected with the *Time* parameter\).

Messages processed by integration flows at runtime consume system memory.

> ### Tip:  
> Memory consumption depends on several factors:
> 
> -   Message throughput
> 
>     The higher the number of messages that are processed within a given time frame, the higher the consumption of memory. In addition, you can expect that consumption increases with message sizes.
> 
> -   Integration flow design
> 
>     An integration flow can contain steps with a particularly high demand for memory, such as \(but not limited to\) Groovy scripts and message mappings.

> ### Note:  
> The *Time* filter element allows you to select the time interval \(options: *Past Day*, *Past Week*, *Past Month*, or *Custom*\).
> 
> When you've selected the option *Custom* for the *Time* filter, you can select date and time with a graphical element with two components: a calendar element and a circular watch element. To select the date, interact with the calendar element and choose a specific day. To select the time, manipulate two separate circles on the watch element to set the desired hour ante meridiem \(am\) and post meridiem \(pm\), respectively. You can select valid dates only; selection of dates in the future is disabled.
> 
> You can select dates up to 30 days in the past.

The message throughput is plotted in two charts against time.

-   The total count of message processing logs \(MPLs\) for a given time period \(as selected with the *Time* parameter\) is plotted in a bar chart.

    The number of MPLs is identical to the number of messages processed during the selected time period.

-   The maximum message size within this time period is plotted in a line chart with a green bullet.


In addition, time periods during which a memory exhaustion was observed are marked in red on the horizontal axis.

The duration covered by a bar represents the value during:

-   One hour when *Past Day* is selected as *Time* 

-   One day when *Past Week* or *Past Month* is selected as *Time* 


Click a bar to get more context information and to get access to the following functions \(the results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the selected time period \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Inspect Usage*

    Navigate to the *Top Integration Flows* screen that allows you to inspect memory allocation by integration flows in more detail.


*Zoom Out* and *Zoom In* to extend/reduce the selected time period. 

> ### Note:  
> The system updates resource consumption on an hourly basis. That means, that there can be a maximum lag of 1 hour between the processing of an integration flow consuming system resources and the *Inspect* feature to show the impact of this integration flow.



<a name="loioe9617dd737384100b96194d37badbb80__section_tqd_3w1_bxb"/>

## Top Integration Flows

On the *Top Flows by Memory Allocation* screen, you can identify the integration flows that are the top consumers of memory, as indicated by the blue shades. These enable a relative comparison between integration flows regarding the amount of allocated memory.

> ### Tip:  
> Memory is continuously allocated for processing messages, and it is automatically reclaimed by garbage collection when it’s no longer used. The chart shows memory allocation. It allows you to do a relative comparison of integration flows with regard to memory consumption.

See: [Inspect Integration Flows By System Memory Usage](inspect-integration-flows-by-system-memory-usage-2a2e1f2.md)



<a name="loioe9617dd737384100b96194d37badbb80__section_vgy_pw5_ywb"/>

## What to Do in Critical Situations

If memory exhaustions have been detected, you can identify the corresponding integration flow and flow step on the *Top Flows by Memory Allocation* screen.

Consider the following recommendations for specific flow steps to mitigate memory exhaustion situations.

-   General integration flow design measures

    You can design integration flows in such a way that memory consumption is minimized.

    More information: [Optimize Memory Footprint](optimize-memory-footprint-dc24074.md)

-   *Script* step

    When using XMLSlurper or JSONSlurper in a script, check out the following SAP Community blog: [Stream the XMLSlurper input in Groovy Scripts](https://blogs.sap.com/2017/06/20/stream-the-xmlslurper-input-in-groovy-scripts/).

    In general, avoid getting the message body as String wherever possible. If you wish to implement a mapping, consider using a *Message Mapping* for XML or JSON payloads.

-   JDBC adapter

    When using the JDBC receiver adapter, make sure that not too many records are loaded per request. Otherwise, the memory can be overloaded.

-   *Splitter* step

    When using Splitter steps, an incoming message can spawn many messages by placing a high load on memory. If you use an *Iterating Splitter* with parallel processing enabled, consider reducing the number of parallel processes. In other cases, consider reducing the bulk size and/or the rate of incoming messages.

    More information: [Reduce the Memory Consumption for Splitter Scenarios](reduce-the-memory-consumption-for-splitter-scenarios-de974b8.md)

-   Mapping

    Mappings can require a high degree of memory allocation. Therefore, consider reducing the rate of incoming messages in case of memory shortages.


