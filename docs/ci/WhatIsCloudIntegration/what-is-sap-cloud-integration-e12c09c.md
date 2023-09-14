<!-- loioe12c09cc8e9b4574b092d8964b049ce6 -->

# What Is SAP Cloud Integration?

Support end-to-end process integration through the exchange of messages. 

SAP Cloud Integration helps you to connect cloud and on-premise applications with other SAP and non-SAP cloud and on-premise applications. This service can process messages in real-time scenarios spanning different companies, organizations, or departments within one organization.

> ### Note:  
> SAP Integration Suite combines Cloud Integration, API Management, Integration Advisor, Open Connectors, and other integration capabilities into a cohesive and simplified toolkit for enterprise integration. To provide a comprehensive integration experience, these services are not available separately, but only as part of the Integration Suite service plan. To learn more on different service plans, see the [Integration Suite](https://discovery-center.cloud.sap/#/serviceCatalog/f810c887-8d25-4942-9849-354837951066) service catalog.



## Environment

This service runs in the Neo and Cloud Foundry \(CF\) environments. Integration content artifacts designed in the Neo environment are also compatible in Cloud Foundry environment with certain limitations as mentioned in the following.

> ### Remember:  
> There are currently certain limitations when working in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).



## Features


<dl>
<dt><b>

Implement diverse scenarios

</b></dt>
<dd>

Integrate processes and data in application-to-application \(A2A\) and business-to-business \(B2B\) scenarios.



</dd><dt><b>

Connect to multiple endpoints

</b></dt>
<dd>

Integrate various applications and data sources from SAP and non-SAP, on premise, as well as the cloud. SAP Cloud Integration comes with a set of prebuilt adapters.



</dd><dt><b>

Customize SAP integration scenarios

</b></dt>
<dd>

Benefit from prepackaged integration content to jump-start integration projects and to set up productive scenarios with only minimum effort. You can extend predefined integration flows according to your requirements.



</dd><dt><b>

Develop custom adapters

</b></dt>
<dd>

Use the adapter SDK to build your own custom adapters for additional connectivity needs.



</dd><dt><b>

Access public APIs

</b></dt>
<dd>

Customize the access to SAP Cloud Integration with our public OData APIs.



</dd><dt><b>

Set up secure and reliable communication

</b></dt>
<dd>

Use our core integration and security capabilities for the safe and reliable processing of messages. Configure how messages are exchanged within an integration scenario so that the data involved is protected according to the newest security standards.



</dd><dt><b>

Implement various communication modes

</b></dt>
<dd>

Orchestrate business processes and integrate data in synchronous as well as in asynchronous scenarios. SAP Cloud Integration also supports reliable messaging processes based on asynchronous decoupling implemented by using queuing mechanisms.



</dd><dt><b>

Integrate with SAP Process Orchestration 

</b></dt>
<dd>

Use SAP Cloud Integration and SAP’s on-premise integration Platform, SAP Process Orchestration, seamlessly integrated.



</dd>
</dl>



<a name="loioe12c09cc8e9b4574b092d8964b049ce6__section_t2h_p31_yfb"/>

## Tools


<table>
<tr>
<th valign="top">

Tools



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

[SAP BTP cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e47748b5bb571014afedc70595804f3e.html)



</td>
<td valign="top">

The cockpit is the central point for managing all activities associated with your subaccount and for accessing key information about your applications.



</td>
</tr>
<tr>
<td valign="top">

[Adapter Development Kit](https://tools.hana.ondemand.com/#cloudintegration)



</td>
<td valign="top">

The Adapter Development Kit allows integration developers to define new adapter types and to integrate them into the Cloud Integration tool environment.



</td>
</tr>
<tr>
<td valign="top">

[Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html)



</td>
<td valign="top">

It serves as the link between on-demand applications in SAP BTP and existing on-premise systems. You can control the resources available for the cloud applications in those systems.



</td>
</tr>
<tr>
<td valign="top">

[Integration Suite Dashboard Overview](https://help.sap.com/viewer/42093f14b43c485fbe3adbbe81eff6c8/release/en-US/a6c514ce6f624a77857f6ff59bbc29cf.html?q=integration%20reporting%20dashboard)



</td>
<td valign="top">

The Cloud Integration reporting dashboard is part of the Integration Suite content package developed on SAP Analytics Cloud. It is a simple and intuitive widget-based analytics dashboard that provides at-a-glance view of relevant key performance indicators of a Cloud Integration tenant. The widgets in the dashboard display data in a simplified way that helps you visualize the context information with slicing and dicing capabilities. If you’re curious to explore, then read the blog on [Interactive Reporting Dashboard for SAP Cloud Integration using SAP Analytics Cloud](https://blogs.sap.com/2020/08/26/sap-analytics-cloud-content-for-sap-cloud-platform-integration/).



</td>
</tr>
</table>



<a name="loioe12c09cc8e9b4574b092d8964b049ce6__section_evb_mvj_srb"/>

## System Scope in the Cloud Foundry Environment

This section describes the system scope for Cloud Integration tenants that are deployed in the Cloud Foundry environment. Read the recommendations to know how to optimize the resources when exceeding the scope:


<table>
<tr>
<th valign="top">

Resource



</th>
<th valign="top">

Scope



</th>
</tr>
<tr>
<td valign="top">

**Integration content**



</td>
<td valign="top">

500 MB

Refer to the blog on [Content Size Limits](https://blogs.sap.com/2020/08/02/cloud-integration-content-size-limits/) learn how to reduce your integration content size.



</td>
</tr>
<tr>
<td valign="top">

**JMS queues**



</td>
<td valign="top">

9 GB, 150 transactions \(default configuration with 30 queues\)

Can be scaled up to 30 GB, 500 transactions \(with 100 queues\)

See the blog on [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) for further guidance on how to set the queue size to restrict the limit and on how to delete unused queues.



</td>
</tr>
<tr>
<td valign="top">

**Message processing log persistence**



</td>
<td valign="top">

35 GB

See: [Cloud Integration – Setting the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)



</td>
</tr>
<tr>
<td valign="top">

**Data store message persistence**



</td>
<td valign="top">

35 GB

See: [Optimize Performance](../Development/optimize-performance-491c80d.md)



</td>
</tr>
<tr>
<td valign="top">

**Disk space**



</td>
<td valign="top">

4 GB

Refer to SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development to prevent the integration flow from running into the “No More Space left on Disk” error.



</td>
</tr>
</table>

For more information on the available data storage features, refer to [Data Storages](../Development/data-storages-31efe35.md).



<a name="loioe12c09cc8e9b4574b092d8964b049ce6__section_psk_1rz_fnb"/>

## System Scope in the Neo Environment

This section describes the system scope for Cloud Integration tenants that are deployed in the Neo environment. Read the recommendation to know how to optimize the resources when exceeding the scope:


<table>
<tr>
<th valign="top">

Resource



</th>
<th valign="top">

Scope



</th>
</tr>
<tr>
<td valign="top">

**Integration content**



</td>
<td valign="top">

500 MB

Refer to the blog on [Content Size Limits](https://blogs.sap.com/2020/08/02/cloud-integration-content-size-limits/) learn how to reduce your integration content size.



</td>
</tr>
<tr>
<td valign="top">

**JMS queues**



</td>
<td valign="top">

9 GB

9 GB, 150 transactions \(default configuration with 30 queues\)

Can be scaled up to 30 GB, 500 transactions \(with 100 queues\)

See the blog on [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) for further guidance on how to set the queue size to restrict the limit and on how to delete unused queues.



</td>
</tr>
<tr>
<td valign="top">

**ASE database**



</td>
<td valign="top">

32 GB

See the following blogs for information on how to:

-   [Avoid Storing Payloads in the Message Processing Log](https://blogs.sap.com/2017/07/24/avoid-storing-payloads-in-the-message-processing-log/)

-   [Avoid Excessive Storage Load caused by Using MPL Attachments](https://blogs.sap.com/2018/02/12/how-to-avoid-excessive-storage-load-caused-by-using-mpl-attachments-for-message-logging/)

-   [Set the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)




</td>
</tr>
<tr>
<td valign="top">

**Disk space**



</td>
<td valign="top">

2 GB

Refer to SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development to prevent the integration flow from running into the “No More Space left on Disk” error.



</td>
</tr>
</table>

For more information on the available data storage features, refer to [Data Storages](../Development/data-storages-31efe35.md).



<a name="loioe12c09cc8e9b4574b092d8964b049ce6__section_j3h_p31_yfb"/>

## Pricing and Resources

Get access to SAP Cloud Integration community, pricing models and all the technical resources, tutorials, blogs, and support you need. Get Started with [SAP Cloud Integration](https://cloudplatform.sap.com/capabilities/product-info.SAP-Cloud-Platform-Integration.cceaaf2b-8ceb-4773-9044-6d8dad7a12eb.html).

