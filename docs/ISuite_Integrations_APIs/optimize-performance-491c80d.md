<!-- loio491c80d16c3547c3b124cf38857f1332 -->

# Optimize Performance

Learn how to improve performance of your integration scenario.

Performance of integration scenarios highly depends on the design of the involved integration flows. Therefore, make sure to consider performance impact when designing integration flows and to avoid using components that can create performance bottlenecks.

Performance can have also an impact on memory footprint or the other way around. Often one influences the other. It's important to consider the effects of the taken decisions and find a balance between performance and memory consumption.

The following design considerations affect performance:



<a name="loio491c80d16c3547c3b124cf38857f1332__section_rtc_4hg_npb"/>

## Message Size

An incoming 1-KB message is processed faster and with less resources than a 5-MB message \(for the same integration flow design\). In particular, if your integration scenario uses many message transformation steps, make sure to process only messages that don't exceed the following size:

-   Payload size: 40 MB

-   Aggregated size for attachments: 100 MB


Following this recommendation helps you to avoid memory bottlenecks. Note that, however, there's no general maximum message size. If the integration flow is designed resource-efficient, it can process way larger messages.

SAP is doing the general capacity management of all your SAP Integration Suite tenants, either of productively used tenants or test tenants. Capacity management is also based on the license model. Therefore, you don't need to care about that. However, memory is a limited resource in the Java virtual machines. Before you use your integration flows productively, it's recommended to perform extensive load testing. Try to use the maximum load for your test that you can expect in productive use and don't concentrate on isolated tests only. You can expect that the productive tenant doesn't process just 1 single integration flow. Therefore, choose a realistic tenant load profile as well. Consider doing this test not at the last minute of your development phase, because an integration flow redesign for performance optimizations can take some time.

> ### Note:  
> If you've designed the integration flow in a performance-friendly way but still the performance isn't good, you can get in touch with SAP to check the tenant resources. Alternatively, check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).



<a name="loio491c80d16c3547c3b124cf38857f1332__section_c5m_fqz_qpb"/>

## Push Messages Versus Timer-Triggered Messages

Sending out messages from a sender system to Cloud Integration can be scaled horizontally in a good way. In contrast to that, using a *Timer* event to start a message processing means to always have exactly 1 process is running at the same time, independent of the scheduled interval.

Therefore, if a high data throughput is desired, prefer designing the integration flow so that it's triggered by messages sent from a sender component rather than by a *Timer* event.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_upx_psz_qpb"/>

## Number of Integration Flow Steps

Every executed step of an integration flow is consuming CPU processing time and memory. Therefore, every additional step increases the overall execution time. An integration flow with only 1 mapping is executed faster than an integration flow with 10 mappings.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_w11_5sz_qpb"/>

## Integration Flow Step Type

Different integration flow steps have different impact. Setting a header via a *Content Modifier* is less time- and resource-consuming than converting a payload into a different format. Security operations like encrypting or signing consume even more CPU.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_c2k_ysz_qpb"/>

## Adapter Type

An adapter type that does a validation of the message syntax, such like the SOAP adapter, takes more time than an adapter where no transformation happens, such like the HTTP adapter.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_k2x_ctz_qpb"/>

## Number of External Calls

Calling systems outside of SAP Integration Suite for content lookup, intermediate updates, or other purposes increases the overall processing time of an integration scenario.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_ogj_gtz_qpb"/>

## Network Latency

Calling a system that is located close to the datacenter where your SAP Integration Suite tenant is running is faster than calling a system that is located further away from the datacenter due to network latency.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_fzf_ktz_qpb"/>

## Memory Versus Database

Using the data store or local/global variables, you store data in the tenant database.

Using database persistency is consuming additional time by writing the content to the database. Keeping data in memory is faster. Nevertheless, storing large data in memory has other risks \(see the considerations about message size\).



<a name="loio491c80d16c3547c3b124cf38857f1332__section_o3n_ttz_qpb"/>

## Number Integration Flows Executed in Parallel

If 1 integration flow is running in an isolated way and no other integration flow is executed in parallel, performance is typically better than when one or multiple integration flows are running in parallel. However, the overall behavior depends on the type and number of integration flow steps. If 1 integration flow is memory-intense, another one is CPU-intense, and a 3rd one is waiting for an external communication partner, it can be that there's no significant difference regarding performance between the integration flows.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_uqz_l5z_qpb"/>

## Pagination for REST/OData Queries

Rest or OData calls to an external system retrieving a high data volume can lead to memory problems or even timeouts. A good practice to increase the robustness and to reduce the memory consumption is to avoid fetching all data at once. This behavior can be achieved by fetching the data in steps using the pagination feature. Even though pagination increases the overall processing time due to additional calls, in some cases pagination can improve the performance. This is the case in particular when the receiver system doesn't support efficient processing of high volume data and when a bad response time can be expected in such a case.

It's recommended to balance the impact of fewer calls with high volume versus a high number of calls with small data volume. To find out what works best, tests must be conducted with real data to find out the ideal configuration.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_egr_dvz_qpb"/>

## Parallel Processing of Steps

Certain integration flow steps allow parallel processing \(for example, the *Multicast* step and the *Splitter* steps\). Generally speaking, parallel processing increases performance. However, parallel processing can lead also to unexpected problems if the backend system can't handle the load of the parallel calls.

Furthermore, not in all situations parallel processing is possible, for example if you want to use database operations in sub branches while having a JDBC transaction enabled.

When activating parallel processing for the *Splitter* step you have to configure a timeout, after which the processing gets interrupted and the integration flow continues with the next steps after the *Splitter*. No error occurs during integration flow processing. Therefore, test the integration flow with the largest expected number of split items and check that the defined timeout fits.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_ifv_4vz_qpb"/>

## Session Reuse for HTTP-Based Adapters

Authentication and the creation of the session on the server can be a costly process. Therefore, reusing the same session can improve the performance of the scenario significantly. Most HTTP-based adapters \(SOAP, IDOC, HTTP, XI, and so forth\) allow session reuse. That means, that the first call to a server generates a session cookie and subsequent calls in the same or future integration flow processings can be done with the same cookie, depending on the configuration. Refer to the following guidelines for more information: [Specify Proper Session Handling](specify-proper-session-handling-06a28e0.md).



<a name="loio491c80d16c3547c3b124cf38857f1332__section_chk_xvz_qpb"/>

## Call Timeouts

Tune the external call timeouts to a reasonable time to match the system waiting time. Complex operations can take long times and the consumption of resources for a transaction lasts that time. While those resources are being consumed, this can affect other integration flows negatively. Try with the biggest expected messages to find out the reasonable timeouts.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_mdg_bwz_qpb"/>

## Maximum Number of Retries

For the case that an error occurs, for example due to internet connectivity or backend server issues, it is possible to implement retry mechanisms. However, retries must be based on the error type. Not all errors are relevant for retry mechanism. Control in your integration flows what kind of errors must be retried and the maximum number of retries to avoid unnecessary executions and thus unnecessary consumption of resources, which could cause performance issues.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_d3b_hwz_qpb"/>

## Batch API Calls

Use batch processing whenever possible instead of reading or updating records one at a time. Test with the biggest expected data to set the batch sizes as large as possible avoiding timeouts. Refer to the following guidelines for more information: [Perform OData Batch Requests](perform-odata-batch-requests-b0372d4.md).



<a name="loio491c80d16c3547c3b124cf38857f1332__section_fhy_nwz_qpb"/>

## API Query Recommendations

In order to avoid unnecessary data volumes, use filters and don't query properties or expand entities you don't need.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_qsw_pwz_qpb"/>

## Multiple Runtime Nodes/Worker Nodes

If you've designed the integration flow in a performance-friendly way but still the performance isn't good, you can get in touch with SAP Operations to check the tenant resources.



<a name="loio491c80d16c3547c3b124cf38857f1332__section_evr_twz_qpb"/>

## Optimize Integration Flow Footprint

When using multicasts, splitters, or subprocesses, It's a good practice to remove all data that isn't needed in the subsequent steps \(body or variables\). Otherwise, the data is kept in memory until the end of the process. Refer to the following guidelines for more information: [Optimize Memory Footprint](optimize-memory-footprint-dc24074.md).



<a name="loio491c80d16c3547c3b124cf38857f1332__section_oy5_zwz_qpb"/>

## Tracing and Logging

Using tracing to analyze an integration flow is highly recommended. However, be aware of the fact that when the *Trace* log level is activated the performance can be reduced. This is due to the fact that collecting and writing all tracing data consumes time and resources. Keep tracing off unless troubleshooting is needed.

Using MPL attachments for logging of your productive scenarios is a valid approach. However, excessive logging can have a negative impact on the performance. Therefore, keep the usage of logging to the necessary minimum and use external parameters to activate or de-active logging.

