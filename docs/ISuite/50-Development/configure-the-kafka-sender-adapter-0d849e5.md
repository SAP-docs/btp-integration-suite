<!-- loio0d849e5b2ea749ff890d7e78db2f3a0b -->

# Configure the Kafka Sender Adapter

You use the Kafka Sender adapter to connect to an external Kafka broker via Kafka protocol and to fetch messages.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio0d849e5b2ea749ff890d7e78db2f3a0b__section_vrm_s4g_p4b"/>

## Configuration

Once you’ve created a sender channel and selected the Kafka sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> -   *Key & Value Deserializer* Key Deserializer will be set to StringDeserializer and Value Deserializer will be set to ByteArrayDeserializer \(Kafka settings: `key.deserializer` and `value.deserializer`\).
> 
> -   *Max. processing time of 1 day* If the message processing exceeds 1 day, the consumer is replaced on broker side \(Kafka setting `max.poll.interval.ms` is set to 86400000\).
> 
> -   *New consumer groups* New consumer groups consume from the latest offset \(Kafka setting `auto.offset.reset` is set to LATEST\).
> 
> -   *Auto commit* Successfully processed records \(offsets\) will be automatically committed in 5 second intervals \(Kafka settings `enable.auto.commit` is set to true and `auto.commit.interval.ms` is set to 5000\).

The following values are displayed in the *General* tab after a channel has been established. If you want to change the configurations, you need to configure a new channel.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name/Adapter Type*

</td>
<td valign="top">

Kafka

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol*

</td>
<td valign="top">

TCP

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol*

</td>
<td valign="top">

Kafka

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows:

> ### Note:  
> -   *Connectivity Settings*: Whenever you change the connectivity settings \(Keystore or Security settings\), you need to redeploy your integration flow or restart the integration flow content for the changes to become effective.
> 
> -   *Polling Status Monitoring*: After deployment of the integration flow with the Kafka Sender adapter, if there's an exception thrown during polling for whichever reason \(for example, connectivity or authentication issues\), the corresponding error details are shown in the “Error Details” pane of the *Manage Integration Content* section of the [Monitor Integrations](monitor-integrations-05446d0.md) UI. In case of an exception, the deployment status is set to “Error” until the exception is resolved.
> 
>     For more information, see also the blog [Monitoring Polling Status in Kafka Sender Adapter](https://blogs.sap.com/2021/08/11/cloud-integration-monitoring-polling-status-in-kafka-sender-adapter/).

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Host*

</td>
<td valign="top">

Enter a bootstrap server \(host:port\). You can add multiple hosts by using a new entry for each bootstrap server.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the type of authentication for connecting to the broker. SASL is selected by default.

-   SASL

-   Client Certificate \(security protocol: SSL\)




</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Select this option to switch between `SASL_SSL` and `SASL_PLAINTEXT`.

> ### Note:  
> Make sure that the root certificate of the broker is uploaded to the keystore. You can access it directly, via *TLS Connectivity Test*. See [Managing Keystore Entries](managing-keystore-entries-2dc8942.md) and [TLS Connectivity Tests](tls-connectivity-tests-03bbb5d.md).



</td>
</tr>
<tr>
<td valign="top">

*SASL Mechanism*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Select the SASL mechanism.

-   PLAIN

-   SCRAM-SHA-256

-   SCRAM-SHA-512




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if *SASL* is selected for *Authentication*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the user credential on the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Client Certificate* is selected for *Authentication*\)

</td>
<td valign="top">

Enter the Private Key Alias.

</td>
</tr>
</table>

> ### Note:  
> The Kafka Sender Adapter supports the following TLS versions:
> 
> TLS 1.0, TLS 1.1, TLS 1.2 and TLS 1.3.
> 
> By default the Kafka Sender Adapter supports TLS 1.3 as preferred version.
> 
> It is highly recommended to use TLS 1.2 or TLS 1.3.

Select the *Processing* tab and provide values in the fields as follows:

> ### Note:  
> The integration flow id acts as Consumer Group.

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Topic*

</td>
<td valign="top">

Enter the name of one or multiple topics you consume from.

> ### Note:  
> The topic name is restricted to `[a-zA-Z0-9\\._\\-]`, it may either contain a . \(dot\), or \_ \(underscore\), but not both and has a maximum length of 249 characters.

If you want to add multiple topics, you can either separate the topic names by comma \(no blank space\) or provide a simple pattern with \*.

> ### Note:  
> Comma-separated: `topic1,topic2,topic3` 
> 
> Simple pattern: `topic*`



</td>
</tr>
<tr>
<td valign="top">

*Parallel Consumers*

</td>
<td valign="top">

Specify how many parallel consumers \(per worker node\) can consume from partitions. This parameter depends on how topics are partitioned. The max. number of parallel consumer is defined as 25 and scales with the number of worker nodes.

</td>
</tr>
<tr>
<td valign="top">

*Error Handling*

</td>
<td valign="top">

Choose between the following options:

-   *Retry Failed Message*: Select to retry the same offset in case of failed message processing.

-   *Skip Failed Message*: Select to continue with the next offset even in case of a failed message \(at-most-once semantics\).




</td>
</tr>
</table>

Select the*Advanced* tab and provide values in the fields as follows:

> ### Note:  
> -   Each of the following parameters has a preconfigured default mode. It isn’t possible to empty a field by deleting the parameter. Always provide a substitute.
> 
> -   The parameters condition each other, meaning they’re codependant. So, don't enter contradictory data. For example, if you define the *Min. Fetch Size* as 1 Megabyte, you should configure the *Max. Fetch Wait Time \(in ms\)* accordingly, allowing enough time to actually collect 1 Megabyte.

**Advanced**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Min. Fetch Size \(in bytes\)*

</td>
<td valign="top">

Define the min. amount of data the server should return for a fetch request.

> ### Tip:  
> Kafka setting:`fetch.min.bytes`



</td>
</tr>
<tr>
<td valign="top">

*Max. Fetch Size \(in bytes\)*

</td>
<td valign="top">

Define the max. amount of data the server should return for a fetch request. For example, if a single message exceeds the configured value, it’s fetched nonetheless, but no additional records are batched together with it. Must be at least 1024 KB.

> ### Tip:  
> Kafka setting:`fetch.max.bytes`



</td>
</tr>
<tr>
<td valign="top">

*Max. Partition Fetch Size \(in bytes\)*

</td>
<td valign="top">

Define the max. partition fetch size the server should return for a fetch request.

> ### Tip:  
> Kafka setting: `max.partition.fetch.bytes`



</td>
</tr>
<tr>
<td valign="top">

*Max. Fetch Wait Time \(in ms\)*

</td>
<td valign="top">

Define the max. fetch wait time \(in ms\) to wait for the other fetch size-related options to be reached.

> ### Tip:  
> Kafka setting:`fetch.max.wait.ms`



</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Polled Records*

</td>
<td valign="top">

Define the max. number of polled records included.

> ### Tip:  
> Kafka setting:`max.poll.records`



</td>
</tr>
<tr>
<td valign="top">

*Request Timeout \(in ms\)*

</td>
<td valign="top">

Define the maximum amount of time the client waits for the response of a request. If the response isn’t received, before the timeout elapses, the client resends the request if possible and configured of fails the request if the defined number of retries is already exhausted.

> ### Tip:  
> Kafka setting:`request.timeout.ms`



</td>
</tr>
<tr>
<td valign="top">

*Max. Retry Backoff \(in ms\)*

</td>
<td valign="top">

Define the amount of time to wait before attempting to poll again in a retry case. Choose the amount of time in such a way as to avoid retry loops that are too tight but allow for some interval time.

> ### Tip:  
> Kafka setting:`retry.backoff.ms`



</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in ms\)*

</td>
<td valign="top">

Define how long to wait before reattempting to reconnect to a given host.

> ### Note:  
> Allow enough time to reconnect to the broker in case of prolonged down time.

> ### Tip:  
> Kafka settings: `reconnect.backoff.ms` and `reconnect.backoff.max.ms`



</td>
</tr>
<tr>
<td valign="top">

*Heartbeat Interval \(in ms\)*

</td>
<td valign="top">

Define the expected time between heartbeats to the consumer coordinator.

> ### Note:  
> The Heartbeat Interval shouldn’t be higher than 1/3 of the Session Timeout.

> ### Tip:  
> Kafka setting: `heartbeat.interval.ms`



</td>
</tr>
<tr>
<td valign="top">

*Session Timeout \(in ms\)*

</td>
<td valign="top">

The timeout is used to detect client failures. If no heartbeat is detected within the session timeout, the consumer is assumed to be dead, and will be disconnected and replaced as a consequence.

> ### Tip:  
> Kafka setting: `session.timeout.ms`



</td>
</tr>
</table>



### Message Headers

The Kafka adapter accepts headers on both sender and receiver side:

-   *Kafka Receiver Adapter*: Headers are sent to the broker.

-   *Kafka Sender Adapter*: Record headers are added to message headers. Supported types: String, Integer, Long, Double, Boolean, byte\[\]. Additionally, the sender adds the following headers: `kafka.TOPIC`, `kafka.PARTITION`, `kafka.OFFSET`, `kafka.KEY` and `kafka.TIMESTAMP`. When setting up the integration flow, add them to the allowlist via *Integration Flow* \> *Runtime Configuration* \> *Allowed Header\(s\)* if required. See [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

**Related Information**  


[https://blogs.sap.com/2021/03/16/cloud-integration-what-you-need-to-know-about-the-kafka-adapter/](https://blogs.sap.com/2021/03/16/cloud-integration-what-you-need-to-know-about-the-kafka-adapter/)

[https://blogs.sap.com/2021/08/11/cloud-integration-monitoring-polling-status-in-kafka-sender-adapter//](https://blogs.sap.com/2021/08/11/cloud-integration-monitoring-polling-status-in-kafka-sender-adapter//)

[Manage Integration Content](manage-integration-content-09a7223.md "The Manage Integration Content section provides an overview of integration content artifacts, such as integration flows, that have been deployed on the tenant.")

