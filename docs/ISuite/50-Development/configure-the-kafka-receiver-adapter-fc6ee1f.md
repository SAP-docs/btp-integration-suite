<!-- loiofc6ee1fb1c1843c195f3cc8cdbfd4b15 -->

# Configure the Kafka Receiver Adapter

You use the Kafka Receiver adapter to connect to an external Kafka broker via Kafka protocol.

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



<a name="loiofc6ee1fb1c1843c195f3cc8cdbfd4b15__section_e2j_m4g_p4b"/>

## Configuration

Once you’ve created a receiver channel and selected the Kafka receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> -   *Key & Value Serializer* Key Serializer will be set to StringSerializer and Value Serializer will be set to ByteArraySerializer \(Kafka settings:`key.serializer` and `value.serializer`\).
> 
> -   *Record Key* Record key can be specified via message header `kafka.KEY`.

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
> Whenever you change the connectivity settings \(Keystore or Security settings\), you need to redeploy your integration flow or restart the integration flow content for the changes to become effective.

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
> Make sure that the broker certificate is uploaded to the keystore. You can access it directly, via *TLS Connectivity Test*. See [Managing Keystore Entries](managing-keystore-entries-2dc8942.md) and [TLS Connectivity Tests](tls-connectivity-tests-03bbb5d.md).



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

\(only if *SASL**Authentication*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the user credential on the tenant. is selected for

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Client Certificate* is selected for is selected for *Authentication*\)

</td>
<td valign="top">

Enter the Private Key Alias.

</td>
</tr>
</table>

> ### Note:  
> The Kafka Receiver Adapter supports the following TLS versions:
> 
> TLS 1.0, TLS 1.1, TLS 1.2 and TLS 1.3.
> 
> By default the Kafka Receiver Adapter supports TLS 1.3 as preferred version.
> 
> It is highly recommended to use TLS 1.2 or TLS 1.3.

Select the *Processing* tab and provide values in the fields as follows:

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

Specify the topic you want to send requests to.

> ### Note:  
> The topic name is restricted to `[a-zA-Z0-9\\._\\-]`, it may either contain a . \(dot\) or \_ \(underscore\), but not both and has a maximum length of 249 characters.

You specify one particular topic or you can configure this parameter dynamically by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Acknowledgment*

</td>
<td valign="top">

Define the type of acknowledgments before a request is considered complete. Select between the following options depending on the importance of your request:

-   *Required By All Replicas* \(default\): Wait until all replicas have acknowledged the message. This option offers max. request security.

-   *Required By Leader*: Wait for the acknowledgment of the leader only \(the first broker to respond\) before considering the request completed.

    > ### Note:  
    > In case the leader fails before the request has been forwarded to the replicas, the message is lost.

-   *Not Required*: Don’t expect an acknowledgment.

    > ### Note:  
    > You don't get a notification in case request transfer was unsuccessful.


> ### Tip:  
> Kafka setting: `acks`



</td>
</tr>
<tr>
<td valign="top">

*Max. Request Size \(in KB\)*

</td>
<td valign="top">

Enter the maximum size of a request in KB \(before compression\). This setting limits the number of record batches in a single request, acts as a limit for the uncompressed record batch size and limits the single-record size. It’s strongly recommended to use the max. message size the broker accepts \(broker setting: `message.max.bytes`\) as input.

> ### Tip:  
> Kafka setting: `max.request.size`



</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Inflight Request*

</td>
<td valign="top">

Define the maximum number of unacknowledged requests the client sends on a single connection before blocking. The default is set to 5, but you can in- or decrease this number.

> ### Tip:  
> Kafka setting: `max.in.flight.requests.per.connection`



</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Retries*

</td>
<td valign="top">

Define the max. number of retries, the client attempts to resend any record which fails with a potentially transient error.

> ### Tip:  
> Kafka setting: `retries`



</td>
</tr>
<tr>
<td valign="top">

*Retry Backoff \(in ms\)*

</td>
<td valign="top">

Define the amount of time to wait before attempting to send a retry. Choose the amount of time in such a way as to avoid retry loops that are too tight but allow for some interval time.

> ### Tip:  
> Kafka setting: `retry.backoff.ms` 



</td>
</tr>
<tr>
<td valign="top">

*Compression*

</td>
<td valign="top">

Select the compression type for the \(batched\) request.

Choose between the following compression types supported by Kafka:

-   *None*

-   *GZIP*

-   *LZ4*

-   *SNAPPY*

-   *ZSTD*


> ### Tip:  
> Kafka setting: `compression.type`



</td>
</tr>
<tr>
<td valign="top">

*Enable Batching* \(recommended\)

</td>
<td valign="top">

Select to batch requests and to reduce traffic. If you disable this option, you set this batch size to 0. It’s activated by default.

</td>
</tr>
<tr>
<td valign="top">

*Batch Size \(in KB\)* only if *Enable Batching* is selected

</td>
<td valign="top">

Define the size of the batches. The producer batches records into fewer requests whenever multiple requests are sent to the same partition in a short time. However, SAP Cloud Integration doesn't wait infinitely, before sending the batch. See *Linger \(in ms\)*.

> ### Tip:  
> Kafka setting:`batch.size`



</td>
</tr>
<tr>
<td valign="top">

*Linger \(in ms\)* only if *Enable Batching* is selected

</td>
<td valign="top">

Define the max. amount of time to wait and try to reach the batch size defined in *Batch Size \(in KB\)*. If this time limit has passed, the request is sent out irrespective of whether or not the defined batch size has been reached.

</td>
</tr>
<tr>
<td valign="top">

*Request Timeout \(in s\)*

</td>
<td valign="top">

Define the maximum amount of time the client waits for the response of a request. If the response isn’t received, before the timeout elapses, the client resends the request if possible and configured or fails the request if the defined number of retries is already exhausted.

> ### Tip:  
> Kafka setting: `request.timeout.ms`



</td>
</tr>
<tr>
<td valign="top">

*Max. Blocking Time \(in s\)*

</td>
<td valign="top">

Define how long the KafkaProducer's send\(\), partitionsFor\(\), initTransactions\(\), sendOffsetsToTransaction\(\), commitTransaction\(\), and abortTransaction\(\) methods block.

> ### Tip:  
> Kafka setting: `max.block.ms`



</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in s\)*

</td>
<td valign="top">

Define how long to wait before reattempting to reconnect to a given host.

> ### Note:  
> Allow enough time to reconnect to the broker if there’s a prolonged down time.

> ### Tip:  
> Kafka settings: `reconnect.backoff.ms` and `reconnect.backoff.max.ms`



</td>
</tr>
</table>



### Message Headers

The Kafka adapter accepts headers on both sender and receiver side.

-   *Kafka Receiver Adapter*: Headers are sent to the broker.

-   *Kafka Sender Adapter*: Record headers are added to message headers. Supported types: String, Integer, Long, Double, Boolean, byte\[\]. Additionally, the sender adds the following headers: `kafka.TOPIC`, `kafka.PARTITION`, `kafka.OFFSET`, `kafka.KEY` and `kafka.TIMESTAMP`. When setting up the integration flow, add them to the allowlist via *Integration Flow* \> *Runtime Configuration* \> *Allowed Header\(s\)* if required. See [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

**Related Information**  


[https://blogs.sap.com/2021/03/16/cloud-integration-what-you-need-to-know-about-the-kafka-adapter/](https://blogs.sap.com/2021/03/16/cloud-integration-what-you-need-to-know-about-the-kafka-adapter/)

