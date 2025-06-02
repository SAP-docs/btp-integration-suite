<!-- loio5d2670fdfed640db8fd43991440d6da7 -->

# Configure the XI Receiver Adapter

The XI receiver adapter allows you to connect a tenant to a local Integration Engine in a receiver system. The adapter supports communication over the XI 3.0 protocol.

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

Consider the following when using the XI adapter.

-   Avoid changing the temporary storage location for operative scenarios \(or do this carefully\).

    Such an action can result in data loss. The reason is that outdated messages \(which will not be retried anymore\) can still be stored there, even if you have changed the *Temporary Storage* attribute in the meantime. When you plan to change this attribute, make sure that there are no messages in the temporary storage originally configured.

-   If possible, as *Temporary Storage* use the *JMS Queue* option as it comes with a better performance and reduced database load.

-   Avoid changing the \(sender or receiver\) participant or the channel name in the integration flow.

    The name of the configured *Temporary Storage* is generated based on these names. If you change these names in the integration flow model and deploy the integration flow again, a temporary storage is generated with the new name. However, messages can still be stored in the old storage. These messages will not be retried anymore after the new storage has been created.

-   Apply the right transaction handling.

    JMS queues and data stores support different transactional processing. As there are additional implications of each transactional processing option with other integration flow steps, we urgently recommend following these rules:

    -   If you have selected *JMS Queue* as *Temporary Storage* in an XI receiver adapter and the XI adapter is used in a sequential multicast or splitter pattern as *Transaction Handling* you have to select *Required for JMS*.

        If as *Temporary Storage* you select *Data Store* in an XI receiver adapter and the XI adapter is used in a sequential multicast or splitter pattern as *Transaction Handling* you have to select *Required for JDBC*.

        For the XI receiver adapter no transaction handler is required if the XI adapter is not used in a sequential multicast or in a split scenario.

        For the XI sender adapter, no transaction handler is required.

        There is no distributed transaction support. Therefore, you can't combine JMS and JDBC transactions. As a consequence, transactional behavior can't be guaranteed in scenarios using the XI receiver adapter with JMS storage in multicast scenarios together with flow steps that need a JDBC transaction handler \(like, for example, Data Store or Write Variables\).


-   The XI Adapter can be used in an *Exactly Once* scenario \(as *Quality of Service*\) in the Send step.

-   The XI Adapter can be used in a *Best Effort* scenario \(as *Quality of Service*\) in the Request-Reply step.


> ### Note:  
> -   The XI adapter does not support acknowledgments.
> 
> -   The XI adapter does not support ExactlyOnceInOrder \(EOIO\).

> ### Note:  
> Message attachments are taken over into the resulting XI message. The attachment names are based on the attachment names as defined in the exchange. To set attachment names, you can, for example, use the Script step \(using the `addAttachmentObject` method of interface `Message`, see [SDK API](sdk-api-c5c7933.md)\).
> 
> For the payload, the name `MainDocument` is used in the XI message.

> ### Note:  
> This adapter doesn't support composite messages \(bulk messages\).

When you have created a receiver channel \(with XI adapter selected\), you can configure the following attributes.

Select the *General* tab and provide values in the field as follows.

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

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

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

*Address*

</td>
<td valign="top">

Address under which the local integration engine of the receiver system can be called.

The integration engine address is composed in the following way:

`https://<host name>:<port>/sap/xi/engine?type=receiver&sap-client=<client>`

> ### Note:  
> You can find out the constituents \(HTTPS port\) of the URL by choosing transaction `SMICM` in the receiver system and choosing *Goto* \> *Services*.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

The endpoint URL that has been used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `RealDestinationUrl`\).

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system.

If you are using Edge Integration Cell or Process Orchestration runtime profile:

-   Select *Internet* if you are connecting to a cloud system.

-   If you select *Manual*, you can manually specify the *Proxy Host* and the *Proxy Port* \(by using the corresponding entry fields\).


If you are using SAP Cloud Integration runtime profile:

-   Select *Internet* if you are connecting to a cloud system.

-   Select *On Premise* if you are connecting via Cloud Connector, and use the parameter `Location ID`.




</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Defines how the tenant authenticates itself against the receiver.

There are the following options:

-   *None*

    No authentication is used.

-   *Basic Authentication*

    The tenant authenticates itself against the receiver based on user credentials \(user and password\).

    Note that when this authentication option is selected, the required security artifact \(**User Credentials**\) has to be deployed on the tenant.

-   *Certificate-Based Authentication*

    The tenant authenticates itself against the receiver based on X.509 certificates.

    Note that when this authentication option is selected, the required security artifact \(**Private Key in Keystore**\) has to be deployed on the tenant.

-   *Principal Propagation* 

    The tenant authenticates itself against the receiver by forwarding the principal of the inbound user to the cloud connector, and from there to the back end of the relevant on-premise system. You can only use principal propagation if you have selected *On Premise* as *Proxy-Type* and *Best Effort* as the *Quality of Service*.

    > ### Remember:  
    > When you want to use Principal Propagation as the authentication method to connect with an on-premise system, don't pass any authorization headers. Follow the approach recommended by SAP BTP Connectivity. See: [Authentication to the On-Premise System](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/67b0b94f09f2446598787eea0855e56b.html).

    > ### Note:  
    > This authentication method can only be used with the following sender adapters: HTTP, SOAP, IDoc, XI sender \(and Quality-of-Service Best Effort\).

    > ### Note:  
    > The token for principal propagation expires after 30 minutes.
    > 
    > If it takes longer than 30 minutes to process the data between the sender and receiver channel, the token for principal propagation expires, which leads to errors in message processing.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(Only when you have selected *Basic Authentication* as *Authentication Type*\)

</td>
<td valign="top">

Name of the *User Credentials* artifact that needs to be deployed separately on the tenant \(it contains user name and password for the user to be authenticated\).

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(Only when you have selected *Certificate-Based Authentication* as *Authentication Type*\)

</td>
<td valign="top">

Optional entry to specify the alias of the private key to be used for authentication. If you leave this field empty, the system checks at runtime for any valid key pair in the tenant keystore.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Specifies the amount of time \(in milliseconds\) that the client waits for a response before the http connection is interrupted.

The default value set to 60000 milliseconds \(1 minute\).

</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

\(only if *JMS Queue* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Enables the tenant to send compressed request messages to the receiver \(which acts as WS provider\) and to indicate to the receiver that it can handle compressed response messages.

</td>
</tr>
<tr>
<td valign="top">

*Allow Chunking* 

</td>
<td valign="top">

Used for enabling chunking of data while sending messages.

</td>
</tr>
<tr>
<td valign="top">

*Return HTTP Response Code as Header*

</td>
<td valign="top">

When selected, writes the HTTP response code received in the response message from the called receiver system into the header `CamelHttpResponseCode`.

This feature is disabled by default.

> ### Note:  
> You can use this header, for example, to analyze the message processing run \(when level Trace has been enabled for monitoring\). Furthermore, you can use this header to define error handling steps after the integration flow has called the XI receiver.
> 
> You can't use the header to change the return code since the return code is defined in the adapter and can't be changed.



</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

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

*XI Identifiers for Sender* 

</td>
<td valign="top">

-   *Communication Party*

    Specifies the Communication Party value of the XI sender in the request message sent to the receiver system.

    You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}`. See: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md).

    A communication party typically represents a larger unit involved in an integration scenario. You usually use a communication party to address a company.

-   *Communication Component*

    Specifies the Communication Component value of the XI sender in the request message sent to the receiver system.

    You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}`. See: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md).

    You typically use a communication component to address a business system as the sender or receiver of messages.




</td>
</tr>
<tr>
<td valign="top">

*XI Identifiers for Receiver* 

</td>
<td valign="top">

-   *Communication Party*

    Specifies the Communication Party value of the XI receiver in the request message sent to the receiver system.

    A communication party typically represents a larger unit involved in an integration scenario. You usually use a communication party to address a company.

    You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

-   *Communication Component*

    Specifies the Communication Component value of the XI receiver in the request message sent to the receiver system.

    You typically use a communication component to address a business system as the sender or receiver of messages.

    You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

    > ### Note:  
    > To get this information, go to the receiver system and choose transaction `SLDCHECK`. In section *LCR\_GET\_OWN\_BUSINESS\_SYSTEM*, you find the business system ID \(which typically has the form `<SID>_<client>`\).

-   *Service Interface* and *Service Interface Namespace*

    These attributes specify the service interface that determines the data structure of the request message sent to the receiver system.

    The receiver interface is described according to how interfaces are defined in the Enterprise Services Repository, that means, with a name and a namespace.

    You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

    > ### Caution:  
    > Currently, you can only configure both parameters dynamically or hard-coded. A combination of dynamic configuration and hard-coding is not supported.




</td>
</tr>
</table>

Select the *Delivery Assurance* tab and provide values in the fields as follows.

**Delivery Assurance**


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

*XI Message ID Determination* 

</td>
<td valign="top">

Select this option to specify how the XI Message ID shall be defined.

You can choose among the following options:

-   *Generate* \(default\)

    Generates a new XI message ID.

-   *Reuse*

    Take over the message ID passed with the header `SapMessageIdEx`. If the header is not available in runtime, a new message ID is generated.

-   *Map*

    Maps a source message ID to the new XI message ID.

    For more information on how to use this option in an end-to-end scenario, check out [SAP Community blog Cloud Integration – Configuring ID Mapping in XI Receiver Adapter](https://blogs.sap.com/2018/11/16/cloud-integration-configuring-id-mapping-in-xi-receiver-adapter/)




</td>
</tr>
<tr>
<td valign="top">

*Source for XI Message ID* \(only in case you selected *Map* as *XI Message ID Determination*\)

</td>
<td valign="top">

To map the source message ID to the XI message ID you can enter the source message ID dynamically by using headers or properties:

`${header.headername}`or `${property.propertyname}`

> ### Note:  
> If no header or property is available at runtime, a new message ID is generated.



</td>
</tr>
<tr>
<td valign="top">

*Quality of Service*

</td>
<td valign="top">

Defines how the message \(from the tenant\) is expected to be processed by the receiver.

There are the following options:

-   *Best Effort*

    The message is sent synchronously; this means that the tenant waits for a response before it continues processing.

    No temporary storage of the message needs to be configured, as message request and response are processed immediately after one another.

-   *Exactly Once*

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing. It is expected that the receiver guarantees that the message is processed exactly once.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is successfully stored there, the sender receives a successful status message. If an error occurs, the message is retried from the temporary storage.

-   *Handled by Integration Flow*

    Quality of service is managed within the integration flow itself, and the XI adapter doesn't add any quality of service handling \(such as retry storage or duplicate checks\).

    The XI sender channel sets the headers `SapQualityOfService` and `SapQueueId` for the XI quality of service and queue ID of the incoming message. These headers can also be used to set the quality of service and queue ID for the message to be processed by the XI receiver channel.

    > ### Remember:  
    > Add the headers `SapQualityOfService` and `SapQueueId` to the list of allowed headers. Otherwise, they won't get propagated to the receiver channel.

    `SapQualityOfService` can have the following values:

    -   `BestEffort`
    -   `ExactlyOnce`
    -   `ExactlyOnceInOrder`

    > ### Note:  
    > *Handled by Integration Flow* is currently not supported when using the XI adapter with Request/Reply and Send steps.




</td>
</tr>
<tr>
<td valign="top">

*Temporary Storage*

\(only if *Exactly Once* is selected for *Quality of Service*\)

</td>
<td valign="top">

Temporary storage location for messages that are processed asynchronously. Messages for which processing runs into an error can be retried from the temporary storage.

You can choose from the following storage types:

-   *Data Store* 

    The message is temporarily stored in the database of the tenant \(in case of an error\). In case of successful message processing, the message is immediately removed from the data store.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Data Stores* tile.

    > ### Note:  
    > The data store name is automatically generated and contains the following parts:
    > 
    > `<name of participant connected with XI adapter>_< XI channel name>`.
    > 
    > This automatically generated name is subject to a length restriction and must not be longer than 40 characters \(including the underscore\). If the data store name exceeds this limit, you must shorten the participant name or the channel name accordingly.
    > 
    > Below the data store name, you find a reference to the associated integration flow in the following form: `<integration flow name>/XI`.

-   *JMS Queue* 

    The message is stored temporarily in a JMS queue on the configured message broker.

    If possible, use this option as it comes with a better performance.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Message Queues* tile.

    > ### Note:  
    > -   The name of the JMS queue is automatically generated and contains the following parts:
    > 
    >     `XI.<Integration Flow Name>.<Channel Name>.<Guid>`.
    > 
    > -   This option is only available if you have an *Enterprise License* or a separate *Enterprise Messaging License*.




</td>
</tr>
<tr>
<td valign="top">

*Number of Concurrent Processes*

\(only if *JMS Queue* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Enter the number of concurrent processes for each worker node. The recommended value depends on the number of worker nodes, the number of queues on the tenant, and the incoming load. Make sure to enter a value that is as small as possible \(1-5\) because JMS resources are limited \(see: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) and [Cloud Integration – Configure Asynchronous Messaging with Retry Using JMS Adapter](https://blogs.sap.com/2017/06/19/cloud-integration-configure-asynchronous-messaging-with-retry-using-jms-adapter/)\).

> ### Note:  
> Default number of concurrent processes is `1`. Increase this number only if parallel processing is required for your scenario. However, be aware of the fact that, when processing large messages, a high number of concurrent processes can lead to out of memory problems.



</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\)*

\(only in case *Exactly One* is selected for *Quality of Service* and *Data Store* is selected for *Temporary Storage*\)

</td>
<td valign="top">

Specify how long the client should wait before trying to process the message again, for example, in the event of a cluster outage. The amount of time you choose should be higher than the processing time.

The default is set to 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Poll Interval \(in s\)*

\(only if *Exactly Once* has been selected for *Quality of Service* and *Data Store* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Specify the poll interval in seconds to wait before consuming messages from the data store. The default is set to 1 s, the max. is set to 300 s.

The adapter continuously consumes messages from the data store if the data store contains entries that are ready to be processed.

The poll interval only becomes effective as soon as the data store doesn't contain such entries anymore. From that point in time, the adapter waits for the time specified by the *Poll Interval* parameter and then again tries to consume messages from the data store.

> ### Note:  
> The smaller the poll interval \(for example, 1 s\), the more load is put on the database.



</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in min\)*

</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery \(in case of an error\).

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff*

</td>
<td valign="top">

Select this option to double the retry interval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)*

\(only configurable when *Exponential Backoff* is selected\)

</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is set to 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue*

\(only if as *Temporary Storage* the option *JMS Queue* is selected\)

</td>
<td valign="top">

Select this option to place the message in the dead-letter queue if it cannot be processed after 3 retries causing an out-of-memory. The processing of the message is stopped then.

In such cases, a lock entry is created which you can view and release in the *Monitor* section of the Web UI under *Managing Locks*.

Use this option to avoid out-of-memory situations \(caused in many cases by large messages\).

For more information, read the SAP Community blog [Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/).

</td>
</tr>
<tr>
<td valign="top">

*Compress Stored Message*

\(only if *JMS Queue* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Select this option to compress the message in the JMS queue. Compressing the message reduces disk space usage and network traffic.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message during Persistence* \(only in case you have selected *Exactly Once* as *Quality of Service*\)

</td>
<td valign="top">

Select this option in case the messages should be stored in an encrypted way in the temporary storage. It is recommended to choose this option if the message can contain sensitive data. Note that this setting might decrease performance of the integration scenario.

</td>
</tr>
<tr>
<td valign="top">

*Expiration Period \(in d\)*

</td>
<td valign="top">

Enter the number of days after which the stored messages are deleted \(default is 30\).

</td>
</tr>
</table>



## Explicit Retry Configuration Using Specific Headers

When as *Quality of Service* you have selected *Exactly Once*, you can use certain headers to specify that after a defined number of message retries the message processing is changed in a specific way. For example, you can configure the integration flow so that after 5 retries the message is routed to a specific receiver \(who will then receive an alert email\). You can do this by using one of the following headers in a dynamic expression.

Which header you can use, depends on the kind of temporary storage chosen.

-   If as *Temporary Storage* you have chosen the option *Data Store*, you can use the header `SAP_DataStoreRetries`.

-   If as *Temporary Storage* you have chosen the option *JMS Queue*, you can use the header `SAPJMSRetries`.


> ### Tip:  
> Example
> 
> When as *Temporary Storage* you have chosen the option *Data Store*, you can use the following expression in the route that is supposed to forward the message to the receiver of the alert email:
> 
> `${header.SAP_DataStoreRetries} > '5'`
> 
> In this example, the message is routed to the related receiver after 5 retries.

**Related Information**  


[Managing Data Stores](managing-data-stores-ac39f1d.md "")

[Managing Message Queues](managing-message-queues-cdcce24.md "You can monitor queues that are active for a tenant.")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[https://blogs.sap.com/2018/06/04/cloud-integration-configuring-scenario-using-the-xi-receiver-adapter/](https://blogs.sap.com/2018/06/04/cloud-integration-configuring-scenario-using-the-xi-receiver-adapter/)

[https://blogs.sap.com/2018/06/04/cloud-integration-configuring-scenario-using-the-xi-sender-adapter/](https://blogs.sap.com/2018/06/04/cloud-integration-configuring-scenario-using-the-xi-sender-adapter/)

[https://blogs.sap.com/2018/08/15/cloud-integration-configuring-explicit-retry-in-exception-sub-process-for-xi-adapter-scenarios/](https://blogs.sap.com/2018/08/15/cloud-integration-configuring-explicit-retry-in-exception-sub-process-for-xi-adapter-scenarios/)

[https://blogs.sap.com/2018/09/21/cloud-integration-usage-of-xi-adapter-in-send-and-request-reply-step/](https://blogs.sap.com/2018/09/21/cloud-integration-usage-of-xi-adapter-in-send-and-request-reply-step/)

[https://blogs.sap.com/2018/11/16/cloud-integration-configuring-id-mapping-in-xi-receiver-adapter/](https://blogs.sap.com/2018/11/16/cloud-integration-configuring-id-mapping-in-xi-receiver-adapter/)

