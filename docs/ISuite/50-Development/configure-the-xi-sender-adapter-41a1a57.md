<!-- loio41a1a57bf54644d1bd351ca689cf531d -->

# Configure the XI Sender Adapter

The XI sender adapter allows you to connect a tenant to a local Integration Engine in a sender system.

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



<a name="loio41a1a57bf54644d1bd351ca689cf531d__section_pfdb_wqv_jyd_sfb"/>

## Use

With this adapter, you can connect an on-premise backend system to SAP Cloud Integration. The XI sender adapter communicates \(receive messages\) over the XI 3.0 protocol.



Consider the following when using the XI adapter.

-   Avoid changing the temporary storage location for operative scenarios \(or do it carefully\).

    Such an action can result in data loss. The reason is that outdated messages \(which won't be retried anymore\) can still be stored there, even if you've changed the *Temporary Storage* attribute in the meantime. When you plan to change this attribute, make sure that there are no mire messages in the temporary storage originally configured.

-   If possible, as *Temporary Storage* use the *JMS Queue* option as it comes with a better performance and reduced database load.

-   Avoid changing the \(sender or receiver\) participant or the channel name in the integration flow.

    The name of the configured *Temporary Storage* is generated based on these names. If you change these names in the integration flow model and deploy the integration flow again, a temporary storage is generated with the new name. However, there can still be messages in the old storage. These messages won't be retried after the new storage has been created.

-   Apply the right transaction handling.

    JMS queues and data stores support different transactional processing. As there are additional implications of each transactional processing option with other integration flow steps, we urgently recommend following these rules:

    -   If as *Temporary Storage* you select *JMS Queue* in an XI receiver adapter and the XI adapter is used in a sequential multicast or splitter pattern as *Transaction Handling* you've to select *Required for JMS*.

        If as *Temporary Storage* you select *Data Store* in an XI receiver adapter and the XI adapter is used in a sequential multicast or splitter pattern as *Transaction Handling* you've to select *Required for JDBC*.

        For the XI receiver adapter, no transaction handler is required if the XI adapter isn't used in a sequential multicast or in a split scenario.

        For the XI sender adapter, no transaction handler is required.

        There's no distributed transaction support. Therefore, you can't combine JMS and JDBC transactions. As a consequence, transactional behavior can't be guaranteed in scenarios using the XI receiver adapter with JMS storage in multicast scenarios together with flow steps that need a JDBC transaction handler \(like, for example, Data Store Operations or Write Variables\).



> ### Note:  
> -   The XI adapter doesn't support acknowledgments.
> 
> -   The XI adapter doesn't support ExactlyOnceInOrder \(EOIO\).
> 
> -   For XI packaging, the incoming package message appears in the MPL.

When you've created a sender channel \(with XI adapter selected\), you can configure the following attributes.

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

Address under which a sender system can reach the tenant.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



</td>
</tr>
<tr>
<td valign="top">

*Authorization* 

</td>
<td valign="top">

Specifies the authorization option for the sender.

> ### Note:  
> The option *client certificate* is not recommended. Instead, it is recommended to use the more secure option *role-based authorization with certificate-to-user mapping*.

You can select one of the following options:

-   *Client Certificate*: Sender authorization is checked on the tenant by evaluating the subject/issuer distinguished name \(DN\) of the certificate \(sent together with the inbound request\). You can use this option together with the following authentication option: *Client-certificate authentication \(without certificate-to-user mapping\)*.

-   *User Role*: Sender authorization is checked based on roles defined on the tenant for the user associated with the inbound request. You can use this option together with the following authentication options:

    -   *Basic authentication* \(using the credentials of the user\)

        The authorizations for the user are checked based on user-to-role assignments defined on the tenant.

    -   *Client-certificate authentication and certificate-to-user mapping*

        The authorizations for the user derived from the certificate-to-user mapping are checked based on user-to-role assignments defined on the tenant.



Depending on your choice, you can also specify one of the following properties:

-   *Client Certificate*

    Allows you to select one or more client certificates \(based on which the inbound authorization is checked\).

    Choose *Add* to add a new certificate for inbound authorization for the selected adapter. You can then select a certificate stored locally on your computer. You can also delete certificates from the list.

    For each certificate, the following attributes are displayed: *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the certificate authority that issues the certificate\).

-   *User Role*

    Allows you to select a role based on which the inbound authorization is checked.

    Choose *Select* to get a list of all available roles.

    The role *ESBMessaging.send* is provided by default. It is a predefined role provided by SAP that authorizes a sender system to process messages on a tenant. However, using SAP BTP Cockpit, you can also define *custom roles* for the runtime node as well. When you choose *Select*, a selection of all custom roles defined that way is offered.

    > ### Note:  
    > Note the following:
    > 
    > -   You can also type in a role name. This has the same result as selecting the role from the value help: Whether the inbound request is authenticated depends on the correct user-to-role assignment defined in SAP BTP Cockpit.
    > 
    > -   When you externalize the user role, the value help for roles is offered in the integration flow configuration as well.
    > 
    > -   If you have selected a product profile for SAP Process Orchestration, the value help will only show the default role *ESBMessaging.send*.




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

*XI Receiver Identifiers for Response*

</td>
<td valign="top">

-   *Communication Party*

    Specify the communication party for the response. Per default, no party is set. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.

    > ### Note:  
    > You can't define the fields dynamically if you choose *Exactly Once* from Delivery Assurance options. In this case, the defined or default values are taken.

-   *Communication Component*

    Specify the communication component for the response. The default is DefaultXIService. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.

    > ### Note:  
    > You can't define the fields dynamically if you choose *Exactly Once* from Delivery Assurance options. In this case, the defined or default values are taken.




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

*Quality of Service*

</td>
<td valign="top">

Defines how the message \(from the sender\) is processed by the tenant.

There are the following options:

-   *Best Effort*

    The message is sent synchronously; this means that the tenant waits for a response before it continues processing.

    No temporary storage of the message needs to be configured as message request and response are processed immediately after another.

-   *At Least Once*

    The message is sent asynchronously. This means that an immediate response is given back to the sender system and the message is retried from the temporary storage to ensure a processing of the message.

    This option guarantees that the message is processed at least once on the tenant. If a message with identical XI message ID is received multiple times from a sender, all of them are processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is successfully stored there, the sender receives a successful status message. If an error occurs, the message is retried from the temporary storage.

-   *Exactly Once* \(only possible if as *Temporary Storage* the option *Data Store* is selected\)

    The message is sent asynchronously. This means that an immediate response is given back to the sender system and the message is retried from the temporary storage to ensure a processing of the message.

    This option guarantees that the message is processed exactly once on the tenant. If a message with identical XI message ID is received multiple times from a sender, only the first one will be processed. The subsequent messages can be identified as duplicates \(based on the value of the message header `SapMessageIdEx`, see as follows\) and won't be processed.

    > ### Note:  
    > For *Exactly Once* handling, the sender XI adapter saves the protocol-specific message ID in the header `SapMessageIdEx`. If this header is set, XI receiver uses the content of this header as the message ID for outbound communication. Usually, this is the desired behavior and enables the receiver to identify any duplicates. However, if the sender system is also the receiver system, or several variants of the message are sent to the same system \(for example, in an external call or multicast\), the receiver system will incorrectly identify these messages as duplicates. In this case, the header `SapMessageIdEx` must be deleted \(for example, using a content modifier\) or overwritten with a new generated message ID. This deactivates *Exactly Once* processing \(that is, duplicates are no longer recognized by the protocol\).
    > 
    > The adapter sets the header `SapQualityOfService`. Its value indicates the quality of service from the sender system.
    > 
    > Possible Values for `SapQualityOfService`:
    > 
    > -   `BestEffort`
    > 
    > -   `ExactlyOnce`

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

\(only if *Exactly Once* or *At Least Once* is selected for *Quality of Service*\)

</td>
<td valign="top">

Temporary storage location for messages that are processed asynchronously. Messages for which processing runs into an error can be retried from the temporary storage.

You can choose among the following storage types:

-   *Data Store* \(only if *Exactly Once* or *At Least Once* is selected for *Quality of Service*\)

    The message is temporarily stored in the database of the tenant \(in case of an error\). In case of successful message processing, the message is immediately removed from the data store.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Data Stores* tile.

    > ### Note:  
    > The data store name is automatically generated and contains the following parts:
    > 
    > `<name of participant connected with XI adapter>_< XI channel name>`
    > 
    > This automatically generated name is subject to a length restriction and must be no more than 40 characters \(including the underscore\). If the data store name exceeds this limit, you must shorten the participant name or channel name accordingly.
    > 
    > After the data store name, you find a reference to the associated integration flow in the following form: `<integration flow name>/XI`

-   *JMS Queue* \(only if *At Least Once* is selected for *Quality of Service*\)

    The message is stored temporarily in a JMS queue on the configured message broker.

    If possible, use this option as it comes with a better performance.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Message Queues* tile.

    > ### Note:  
    > -   For this option, only *Quality of Service ALO* \(At Least Once\) is supported.
    > 
    > -   The name of the JMS queue is automatically generated and contains the following parts:
    > 
    >     `XI.<Integration Flow Name>.<Channel Name>.<Guid>` 
    > 
    > -   This option is only available if you've an *Enterprise License* or a separate *Enterprise Messaging License*.




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

\(only configurable if *Data Store* has been selected\)

</td>
<td valign="top">

Enter a value for the timeout of the in-progress repository. After this time, a message is retried in case of a cluster outage.

</td>
</tr>
<tr>
<td valign="top">

*Poll Interval \(in s\)*

\(only if *Exactly Once* or *At Least Once* has been selected for *Quality of Service* and *Data Store* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Specify the poll interval in seconds to wait before consuming messages from the data store. The default is set to 1 second, the max. is set to 300 seconds.

The adapter continuously consumes messages from the data store if the data store contains entries that are ready to be processed.

The poll interval only becomes effective as soon as the data store doesn't contain such entries anymore. From that point in time, the adapter waits for the time specified by the *Poll Interval* parameter and then again tries to consume messages from the data store.

> ### Note:  
> The smaller the poll interval \(for example, 1 second or less\), the more load is put on the data store.



</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in min\)*

</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery.

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

\(only configurable if *Exponential Backoff* has been selected\)

</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue*

\(only if *JMS Queue* has been selected for *Temporary Storage*\)

</td>
<td valign="top">

Select this option to place the message in the dead-letter queue if it can't be processed after 3 retries causing an out-of-memory. Processing of the message is stopped then.

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

*Encrypt Message during Persistence* \(only in case you've selected *Exactly Once* as *Quality of Service*\)

</td>
<td valign="top">

Select this option in case the messages should be stored in an encrypted way in the temporary storage.

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



<a name="loio41a1a57bf54644d1bd351ca689cf531d__section_xr3_vpw_q2b"/>

## Explicit Retry Configuration Using Specific Headers

When as *Quality of Service* you have selected *Exactly Once*, you can use certain headers to specify that after a defined number of message retries message processing is changed in a specific way. For example, you can configure the integration flow so that after 5 retries the message is routed to a specific receiver \(who will then receive an alert email\). You can do this by using one of the following mentioned headers in a dynamic expression.

Which header you can use, depends on the chosen kind of temporary storage.

-   If as *Temporary Storage* you have chosen the option *Data Store*, you can use header `SAP_DataStoreRetries`.

-   If as *Temporary Storage* you have chosen the option *JMS Queue*, you can use header `SAPJMSRetries`.


> ### Tip:  
> Example
> 
> When as *Temporary Storage* you have chosen the option *Data Store*, you can use the following expression in the route that is supposed to forward the message to the receiver of the alert email:
> 
> `${header.SAP_DataStoreRetries} > '5'`
> 
> In this example, the message is routed to the related receiver after 5 retries.



Select the *Conditions* tab and specify the following parameter.

**Conditions**


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

Maximum Message Size

</td>
<td valign="top">

This parameter allows you to configure a maximum size for inbound messages \(smallest value for a size limit is 1 MB\). All inbound messages that exceed the specified size \(per integration flow and on the runtime node where the integration flow is deployed\) are blocked.

To configure the maximum message size, you can specify the following parameter:

-   *Body Size \(in MB\)*

-   *Attachment Size \(in MB\)*


If a message is rejected because it exceeds the configured limit, the sender receives an error message.

</td>
</tr>
</table>

**Related Information**  


[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/24585cc503334e6c917ef383efb5558a.html "") :arrow_upper_right:

[Managing Data Stores](managing-data-stores-ac39f1d.md "")

[Managing Message Queues](managing-message-queues-cdcce24.md "You can monitor queues that are active for a tenant.")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[Configuring a Scenario Using the XI Sender Adapter](https://blogs.sap.com/2018/06/04/cloud-integration-configuring-scenario-using-the-xi-sender-adapter/)

[Cloud Integration - Configuring Scenario with XI Sender handling Multiple Interfaces](https://blogs.sap.com/2018/12/04/cloud-integration-configuring-scenario-with-xi-sender-handling-multiple-interfaces/)

[Cloud Integration - Configuring Explicit Retry in Exception Sub-Process for XI Adapter Scenarios](https://blogs.sap.com/2018/08/15/cloud-integration-configuring-explicit-retry-in-exception-sub-process-for-xi-adapter-scenarios/)

