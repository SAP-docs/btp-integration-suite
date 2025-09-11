<!-- loioc0052aed1897446fb607d96a97d7adc2 -->

# Troubleshooting Integration Flows

Information on troubleshooting incidents and errors for Integration Flows.



<a name="loioc0052aed1897446fb607d96a97d7adc2__section_kf3_44x_12c"/>

## Issues while creating an Integration Flow


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top" colspan="2">

Solution

</th>
</tr>
<tr>
<td valign="top">

Unable to load integration flow details

</td>
<td valign="top">

One or more unused components present

</td>
<td valign="top" colspan="2">

Refer [2642034](https://me.sap.com/notes/2642034) - Error while loading details of the integration flow" while opening an integration flow in Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

Unable to import the Process Integration artifact

</td>
<td valign="top">

Integration content archive \(.zip file\) contains unnecessary folders or incorrect structure.

</td>
<td valign="top" colspan="2">

Refer [2440675](https://me.sap.com/notes/2440675)- Unable to import integration flow into Web UI.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

User Interface design issues

</td>
<td valign="top">

When configuring a connection to an on-premise system using a receiver adapter with the *Proxy Type* set to *On-Premise*, then you get a validation error

</td>
<td valign="top" colspan="2">

For the on-premise connectivity, utilize the virtual URL defined in the Cloud Connector instance with the HTTP protocol.

The URL should be in the format: `http://<host>:<port>/<path>` 

</td>
</tr>
<tr>
<td valign="top">

Content Modifier usage issue:

-   Latency in runtime performance because payload is large
-   Line characters are not parsed correctly, resulting in an unexpected output
-   The carriage return character is not retained and is instead converted to a new line



</td>
<td valign="top" colspan="2">

Refer [Define Content Modifier](50-Development/define-content-modifier-8f04a70.md) 

</td>
</tr>
<tr>
<td valign="top">

Mutlicast, Join, Gather issues

</td>
<td valign="top" colspan="2">

Refer

[Define Gather and Join](50-Development/define-gather-and-join-94ef1f2.md)

[Define Multicast](50-Development/define-multicast-17de3ea.md)

For more information, see [3028577](https://me.sap.com/notes/3028577) - Exception Subprocess in SAP Cloud Integration does not execute in case of error on nested multicast branches.

> ### Note:  
> For further issues, create a support ticket on the component *LOD-HCI-PI-GB*.



</td>
</tr>
</table>



<a name="loioc0052aed1897446fb607d96a97d7adc2__section_rd5_jqx_12c"/>

## Issues while deploying an Integration Flow

**Deploying**


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

HTTP 403 error

</td>
<td valign="top">

Integration flow deployment issues

</td>
<td valign="top">

Contact your IT department to whitelist the following custom HTTP methods from SAP Cloud Platform Integration:

-   Update
-   Validate
-   Test
-   Clean
-   Abort
-   Copy\_Resource
-   Copy\_Resource\_Ext
-   HelpService
-   Fetch\_Resource
-   Re\_Bind
-   Close
-   Deploy
-   Migrate
-   Lock
-   Report
-   Checkin
-   Unlock



</td>
</tr>
<tr>
<td valign="top">

All deployment attempts for the artifact failed.

Error: Queue creation failed. Check your JMS queue quota.

</td>
<td valign="top">

This error occurs when the JMS queue limit has been reached when deploying an Integration flow

</td>
<td valign="top">

Refer [Managing Queues](50-Development/managing-queues-f116962.md).

For more information, see

-   [Cloud Integration – Checks in JMS Message Queue Monitor](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-checks-in-jms-message-queue-monitor/ba-p/13347071) 
-   [Cloud Integration- Activating and Managing Enterprise Messaging Capabilities \( AS2, JMS and XI Adapters \) in Neo](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-activating-and-managing-enterprise-messaging-capabilities/ba-p/13392542) 



</td>
</tr>
<tr>
<td valign="top">

-   Error ref: \[CAMEL\]\[IFLOW\]\[ERROR\] : Integration flow failed. \[CAMEL\]\[IFLOW\]\[EXCEPTION\] : java.util.concurrent.TimeoutException



</td>
<td valign="top">

PGP encryptor and/or PGP decryptor failure when deploying an Integration flow

</td>
<td valign="top">

Refer

[Managing PGP Keys](50-Development/managing-pgp-keys-cd478a7.md)

[Deploying a PGP Public Keyring](50-Development/deploying-a-pgp-public-keyring-7f04458.md)

[Deploying a PGP Secret Keyring](50-Development/deploying-a-pgp-secret-keyring-9d8e1a9.md)

> ### Note:  
> For futher issues, create a support ticket on the component *LOD-HCI-PI-RT*.



</td>
</tr>
</table>



<a name="loioc0052aed1897446fb607d96a97d7adc2__section_b1t_4qx_12c"/>

## Issues while running an Integration Flow

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Unable to debug issues from MPL

</td>
<td valign="top">



</td>
<td valign="top">

Refer

[2508723](https://me.sap.com/notes/2508723) - CPI: MPL of a Failed Message at Debug Level.

[2665258](https://me.sap.com/notes/2665258) - How to trace message contents in Cloud Integration \(CPI\).

For more information, see [Tracing the Execution of an Integration Flow](50-Development/tracing-the-execution-of-an-integration-flow-4ec27d3.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Timeout Errors

</td>
<td valign="top">

Socket Time Out errors during:

-   Connection to a server
-   Communication



</td>
<td valign="top">

-   Type A

    For Reference on SocketTimeOut : [https://cwiki.apache.org/confluence/display/HADOOP2/SocketTimeout](https://cwiki.apache.org/confluence/display/HADOOP2/SocketTimeout)

    For more information, see

    -   [https://help.sap.com/docs/btp/sap-btp-neo-environment/regions-and-hosts-available-for-neo-environment?version=Cloud](https://help.sap.com/docs/btp/sap-btp-neo-environment/regions-and-hosts-available-for-neo-environment?version=Cloud)
    -   [https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud)

-   Type B
-   Type C
-   Type D

[2554365](https://me.sap.com/notes/2554365) - Cannot connect to sftp error on Cloud Integration.

[2808441](https://me.sap.com/notes/2808441) - IP address allowlist for Cloud Integration.

[3236873](https://me.sap.com/notes/3236873) - FAQ: IP Allowlisting for Cloud Integration

[2948138](https://me.sap.com/notes/2948138) - How to troubleshoot network connectivity issues between customer network and SAP Data Centers.

</td>
</tr>
<tr>
<td valign="top">

Connection not available

</td>
<td valign="top">

-   Type A

    Refer to the Blog - [Cloud Integration - Using Parallel Processing in General and Iterating Splitter](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-using-parallel-processing-in-general-and-iterating/ba-p/13354217) 

-   [3331596](https://me.sap.com/notes/3331596) -

    Connection is not available, request timed out after \*\*\*ms" error happened during Cloud Integration message processing.




</td>
</tr>
<tr>
<td valign="top">

SocketException - Connection Reset

</td>
<td valign="top">

Refer to the blog:

-   [3212462](https://me.sap.com/notes/3212462) - Intermittent error "Connection reset by peer" in Cloud Integration.
-   [3331226](https://me.sap.com/notes/3331226) - Connection reset \(by peer\)" error happened in an Outbound communication in CPI.
-   [2499167](https://me.sap.com/notes/2499167) - Handling Read timed out and Connection Reset Errors in Cloud Integration.
-   [2967576](https://me.sap.com/notes/2967576) - Root cause analysis of network-related issues in SAP Cloud Platform.
-   [3309287](https://me.sap.com/notes/3309287) - CQC Interface Management Service for CPI iFlows.
-   [973561](https://me.sap.com/notes/973561) - Network related SSL issues.



</td>
</tr>
<tr>
<td valign="top">

TimeOut Exception

</td>
<td valign="top">

Refer to the blog - [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/TimeoutException.html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/TimeoutException.html)

</td>
</tr>
<tr>
<td valign="top">

SocketTimeOut Exception - Read timed out

</td>
<td valign="top">

For more informaation, see [Set a Proper Timeout](50-Development/set-a-proper-timeout-3535f15.md)

[3331631](https://me.sap.com/notes/3331631) - "java.net.SocketTimeoutException: Read timed out" error happened in an outbound communication in CPI.

[3087235](https://me.sap.com/notes/3087235) - Troubleshooting intermittent java.net.SocketTimeoutException: Read timed out in CPI <-\> C4C integrations.

[3001759](https://me.sap.com/notes/3001759) - Error ‘java.net.SocketTimeoutException’ in SOAP 1.x Receiver Adapter in combination with HTTP 500 Internal Server Error – Cloud.

[3263263](https://me.sap.com/notes/3263263) - Read Timeout error in XI adapter

[2499167](https://me.sap.com/notes/2499167) - Handling Read timed out and Connection Reset Errors in Cloud Integration.

[2967576](https://me.sap.com/notes/2967576) - Root cause analysis of network-related issues in SAP Cloud Platform.

</td>
</tr>
<tr>
<td valign="top">

Messages stuck in Processing state. For more information, see [2399949](https://me.sap.com/notes/2399949)

</td>
<td valign="top">

-   Processing time constantly increasing
-   Processing time stopped increasing



</td>
<td valign="top">

Refer [Setting Log Levels](50-Development/setting-log-levels-4e6d3fc.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Database issues. For more information, see [https://help.sap.com/docs/cloud-integration/sap-cloud-integration/types-of-stored-data-neo?version=Cloud](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/types-of-stored-data-neo?version=Cloud)

</td>
<td valign="top">

Database storage is exhausted.

</td>
<td valign="top">

Writing data volume to the database should be limited. For example, Storing message content only during MPL errors.

For more information, see

-   [About Storing Payloads in the Message Processing Log, Especially in Productive Integration Flows](https://community.sap.com/t5/technology-blogs-by-sap/about-storing-payloads-in-the-message-processing-log-especially-in/ba-p/13316488) 
-   [How to Avoid Excessive Storage Load Caused by Using MPL Attachments for Message Logging](https://community.sap.com/t5/technology-blogs-by-sap/how-to-avoid-excessive-storage-load-caused-by-using-mpl-attachments-for/ba-p/13387940) 



</td>
</tr>
<tr>
<td valign="top">

Database connection is exhausted

</td>
<td valign="top">

Refer [2492017](https://me.sap.com/notes/2492017) - SQLNestedException: Cannot get a connection, pool error Timeout waiting for idle object.

</td>
</tr>
<tr>
<td valign="top">

Database operation usage issues

</td>
<td valign="top">

JDBC transaction handling is required to ensure that your database write/delete operations are linked to the message processing status.

JDBC transaction handling is not required.

</td>
</tr>
<tr>
<td valign="top">

Log entries for successfully processed messages are not retained in the MPL.

</td>
<td valign="top">

Refer [2672914](https://me.sap.com/notes/2672914) - Monitor Message Processing is missing MPL entries for messages in CPI.

</td>
</tr>
<tr>
<td valign="top">

Database persistence is impacted by a service disruption, rendering it inaccessible for connections.

</td>
<td valign="top">

> ### Note:  
> For futher issues, create a support ticket on the component *LOD-HCI-PI-OPS*.



</td>
</tr>
<tr>
<td valign="top">

Error: java.io.IOException: Remotely closed

</td>
<td valign="top">

-   Integration flow utilizes an OData receiver adapter and generates a high volume of HTTP requests.
-   The number of concurrent HTTP sessions is limited by the receiver system.



</td>
<td valign="top">

-   Refer to the SAP Community Blog - [Batch Operation in OData V2 Adapter in SAP Cloud Platform Integration](https://community.sap.com/t5/technology-blogs-by-sap/batch-operation-in-odata-v2-adapter-in-sap-cloud-platform-integration/ba-p/13311072) 
-   Refer to the SAP Community Blog - [Cloud Integration - How to configure Session Handling in Integration Flow](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-configure-session-handling-in-integration-flow/ba-p/13325908) 



</td>
</tr>
<tr>
<td valign="top">

Integration flow status - Starting

</td>
<td valign="top">

Issue can occur due to mulitple reasons:

-   Addition of message processing node to the tenant.
-   Node restarted.
-   Node is out of resources.



</td>
<td valign="top">

Refer [Message Processing Log](50-Development/message-processing-log-b32f8cd.md)

Issues recurring due to the tenant, follow these steps:

-   Navigate to the message that is stuck with status "Processing."
-   Record the "Last Updated At" timestamp from the header and the "Process ID" from the Logs section.
-   Go to the "System Log Files" tile within the "Access Logs" section.
-   Use the "Process ID" value from above as a filter.
-   Download the CP Default Trace File that corresponds to the "Last Updated At" timestamp and open it in a text editor.

Issues with OutOfMemoryError or heap space, refer to the below issue.

> ### Note:  
> For further issues, create a support ticket on the component *LOD-HCI-PI-RT*.



</td>
</tr>
<tr>
<td valign="top">

Error: java.lang.OutOfMemoryError: Java heap space

</td>
<td valign="top">

Out of memory occurs if the integration flow processes high volume of messages within short time intervals.

</td>
<td valign="top">

-   Refer SAP Community Blog - [Handling Large Data With SAP Cloud Platform Integration OData V2 Adapter](https://community.sap.com/t5/integration-blog-posts/handling-large-data-with-sap-cloud-platform-integration-odata-v2-adapter/ba-p/13312998) - Usage of OData or SuccessFactors \(OData\) receiver adapter.
-   Configure the inbound adapter to set limits on the size of the message body and/or attachments. For example: configure these settings in the Conditions tab of the sender adapter, such as the SOAP 1.x sender adapter.
-   Refer SAP Community Blog - [Cloud Integration - Using Parallel Processing in General and Iterating Splitter](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-using-parallel-processing-in-general-and-iterating/ba-p/13354217) 

    For more information, see [General and Iterating Splitter](50-Development/general-and-iterating-splitter-b49d088.md) - SAP Help Portal.

-   Refer SAP Community Blog - [Avoid Binding Variables in Groovy Scripts](https://community.sap.com/t5/technology-blogs-by-sap/avoid-binding-variables-in-groovy-scripts/ba-p/13322885) 
-   Refer SAP Community Blog - [Stream the XMLSlurper input in Groovy Scripts](https://community.sap.com/t5/technology-blogs-by-sap/stream-the-xmlslurper-input-in-groovy-scripts/ba-p/13348915) 



</td>
</tr>
<tr>
<td valign="top">

Converter Setup issues

-   Exception: java.lang.NullPointerException: while trying to invoke the method java.util.List.iterator\(\) of a null object loaded from local variable 'asList'
-   Exception : com.sap.it.rt.csvtoxml.converter.exception.CsvToXmlConversionException: XSD schema is incompatible with CSV payload
-   Error: After conversion data in csv file are not proper. You see "?" Marks instead of character in few fields



</td>
<td valign="top">

Issues caused in the Integration flow when using:

-   CSV to XML Converter
-   XML to CSV Converter



</td>
<td valign="top">

Perform the following:

1.  The CSV file should either be enclosed in double quotes or none at all.
2.  Copy the CSV file to the Content Modifier and pass to the CSV to XML Converter.
3.  Insert a Content Modifier before the Converter. In the Header section of the Content Modifier, add an entry with the following details:
    -   *Name*: `CamelCharsetName`
    -   *Type*: `Constant`
    -   *Data Type*: `java.ling.string`
    -   *Value*: `UTF - 16LE`

4.  Specify the correct delimiter used in the CSV file within the converter settings.

> ### Note:  
> For further issues, create a support ticket on the component *LOD-HCI-PI-GB*.



</td>
</tr>
<tr>
<td valign="top">

Timer Setup Issues

</td>
<td valign="top">

Issue caused when either a timer-based sender adapter with scheduler functionality or a Timer start event is present in the Integration flow.

</td>
<td valign="top">

-   Refer

    [Message Processing Log – Text View](50-Development/message-processing-log-text-view-718309a.md)

-   [2552484](https://me.sap.com/notes/2552484) - Unexpected behavior while Scheduling ‘Run Once’ in Start Timer
-   [2582931](https://me.sap.com/notes/2582931) - Multiple MPL Entries Seen With Timer Based Integration Flows
-   [2577093](https://me.sap.com/notes/2577093) - How Timezone and Daylight Saving work in Timer Start

    For more information, see [Daylight Savings in SAP Cloud Integration](https://community.sap.com/t5/technology-blogs-by-sap/daylight-savings-in-sap-cloud-integration/ba-p/13485808) 

-   For customized scheduling, see [Customized Scheduling for integrations in SAP Cloud Integration](https://community.sap.com/t5/technology-blogs-by-sap/customized-scheduling-for-integrations-in-sap-cloud-integration/ba-p/13360922) 
-   [2905759](https://me.sap.com/notes/2905759) - Runtime Error: Integration Flow Stuck in Starting State
-   [3004595](https://me.sap.com/notes/3004595) - Runtime Issue: Integration Flow runs more than once at the scheduled time

> ### Note:  
> For further issues, create a support ticket on the component *LOD-HCI-PI-GB*.



</td>
</tr>
<tr>
<td valign="top">

Decryptor Step Issues

</td>
<td valign="top">

Encounter an error when attempting to send a message through an integration flow that includes the Decryptor step.

</td>
<td valign="top">

Refer [2586949](https://me.sap.com/notes/2586949) - CPI Integration Flow failing after decrypt step

</td>
</tr>
<tr>
<td valign="top">

JMS Queue Issues

</td>
<td valign="top">

Issues encountered during storing or reading messages from JMS queues when using the JMS sender or receiver adapter.

</td>
<td valign="top">

Refer [JMS Adapter](50-Development/jms-adapter-0993f2a.md)

For more information, see

-   [Cloud Integration - Configure Asynchronous Messaging with Retry Using JMS Adapter](https://community.sap.com/t5/integration-blog-posts/cloud-integration-configure-asynchronous-messaging-with-retry-using-jms/ba-p/13315669)
-   [Cloud Integration - JMS Resource and Size Limits](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-jms-resource-and-size-limits/ba-p/13322814)
-   [Cloud Integration - How to configure Transaction Handling in Integration Flow](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-configure-transaction-handling-in-integration-flow/ba-p/13332565)
-   [Cloud Integration- Activating and Managing Enterprise Messaging Capabilities \( AS2, JMS and XI Adapters \) in Neo](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-activating-and-managing-enterprise-messaging-capabilities/ba-p/13392542)
-   [Cloud Integration – Checks in JMS Message Queue Monitor](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-checks-in-jms-message-queue-monitor/ba-p/13347071) 



</td>
</tr>
<tr>
<td valign="top">

Kafka Adapter Issues

</td>
<td valign="top">

Various issues that arise after deploying an integration that utilizes a Kafka adapter

</td>
<td valign="top">

Refer to the blog: [Cloud Integration - What You Need to Know About the Kafka Adapter](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-what-you-need-to-know-about-the-kafka-adapter/ba-p/13495070) 

</td>
</tr>
<tr>
<td valign="top">

XML Parsing Issues

</td>
<td valign="top">

Connection error with the receiver system

</td>
<td valign="top">

Refer

-   [Monitor Message Processing](50-Development/monitor-message-processing-314df3f.md)
-   [Guidelines and Best Practices for Message Monitoring](50-Development/guidelines-and-best-practices-for-message-monitoring-6f598b4.md)



</td>
</tr>
</table>

