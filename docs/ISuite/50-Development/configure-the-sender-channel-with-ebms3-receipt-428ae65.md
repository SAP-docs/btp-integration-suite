<!-- loio428ae6523b61408e9014d55263a47a61 -->

# Configure the Sender Channel with ebMS3 Receipt

Allows the sender channel to transmit the receipt for an incoming push message.



## Context

You configure with the AS4 sender adapter with ebMS3 Receipt to support non-repudiation of receipt, which assures the receiver has received the message without being modified during the message exchange.

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

*Agreement* 

</td>
<td valign="top">

Define the message exchange pattern agreed between the MSHs.

</td>
</tr>
<tr>
<td valign="top">

*Address* 

</td>
<td valign="top">

Specify the relative endpoint of the receiving MSH. For example, `/orders`.

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

Select *User Role* if you want to authorize a user to send message based on the `ESBMessaging.send`.

Select *Client Certificate* if you want to authorize a user to send message based on a certificate. If you select this option, you have to add and enter the Subject DN \(information used to authorize the sender\) and Issuer DN \(information about the Certificate Authority who issues the certificate\).

</td>
</tr>
<tr>
<td valign="top">

*User Role*

\(only if you select *User Role* in *Authorization*\)

</td>
<td valign="top">

Select a role to authorize the user to access the receiving MSH endpoint.

</td>
</tr>
</table>

Select the *Security* tab and provide values in the fields as follows.

**Security**


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

*Verify Username Token*

</td>
<td valign="top">

Select the relevant option for username token verification in the AS4 message:

-   Dynamic: You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound _Receipt_Verify_Username_Token` parameter of partner directory. The valid values are:
    -   notRequired
    -   required

-   Not Required: To skip the verification of response message.
-   Required



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* only if *Verify Username Token* isn't selected as *Not Required*

</td>
<td valign="top">

Define the credential name of the username-password pair specified during the deployment of the security artifact.

</td>
</tr>
<tr>
<td valign="top">

*Save Incoming Receipt* 

</td>
<td valign="top">

Saves the incoming receipt in the message store.

</td>
</tr>
<tr>
<td valign="top">

*Verify the Receipt Signature*

</td>
<td valign="top">

Verifies the signature of the incoming receipt.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias* 

</td>
<td valign="top">

Define the public key alias or aliases to verify the signature of the AS4 message.

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

Defines how the message is processed by the tenant.

There are the following options:

-   *Best Effort*

    The message is sent synchronously; this means that the tenant waits for a response before it continues processing.

    No temporary storage of the message needs to be configured, as message request and response are processed immediately after another.

-   *At Least Once*

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing. It is expected that the receiver guarantees that the message is processed exactly once.

    This option guarantees that the message is processed at least once on the tenant. If a message with identical message ID is received multiple times from a sender, all of them will be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is store there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.

-   *Exactly Once* \(Only possible if as *Temporary Storage* the option *Data Store* is selected\)

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing.

    This option guarantees that the message is processed exactly once on the tenant. If a message with identical message ID is received multiple times from a sender, only the first one will be processed. The subsequent messages can be identified as duplicates and will not be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is store there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.




</td>
</tr>
<tr>
<td valign="top">

*Temporary Storage*

\(only if as *Quality of Service* the option *Exactly Once* or *At Least Once* is selected\)

</td>
<td valign="top">

Temporary storage location for messages that are processed asynchronously. Messages for which processing runs into an error can be retried from the temporary storage.

You can choose among the following storage types:

-   *Data Store*

    The message is temporarily stored in the database of the tenant \(in case of an error\). In case of successful message processing, the message is immediately removed from the data store.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Data Stores* tile.

    > ### Note:  
    > The data store name is automatically generated and contains the following parts:
    > 
    > `<name of participant connected with AS4 adapter>_< AS4 channel name>`
    > 
    > This automatically generated name is subject to a length restriction and must be no more than 40 characters \(including the underscore\). If the data store name exceeds this limit, you must shorten the participant name or channel name accordingly.
    > 
    > Below the data store name, you find a reference to the associated integration flow in the following form: `<integration flow name>/AS4`

-   *JMS Queue*

    The message is stored temporarily in a JMS queue on the configured message broker.

    If possible, use this option as it comes with a better performance.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Message Queues* tile.

    > ### Note:  
    > The name of the JMS queue is automatically generated and contains the following parts:
    > 
    > `AS4.<Integration Flow Name>.<Channel Name>.<Guide>` 

    > ### Note:  
    > This option is only available if you have an *Enterprise Edition* license.




</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\)*

\(only configurable if *Data Store* is selected

</td>
<td valign="top">

Enter a value for the retry timeout of the in-progress repository.

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

\(only configurable when *Exponential Backoff* is selected\)

</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue*

\(only if as *Temporary Storage**JMS Queue* is selected\)

</td>
<td valign="top">

Select this option to place the message in the dead-letter queue if it cannot be processed after three retries caused by an out-of-memory. Processing of the message is stopped then. the option

In such cases, a lock entry is created which you can view and release in the *Monitor* section of the Web UI under *Managing Locks*.

Use this option to avoid out-of-memory situations \(caused in many cases by large messages\).

For more information, read the SAP Community blog [Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/).

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message During Persistence* 

</td>
<td valign="top">

Select this option in case the messages should be stored in an encrypted way during certain processing steps.

</td>
</tr>
</table>

Select the *Conditions* the option tab and provide values in the fields as follows.

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
<td valign="top" colspan="2">

The parameters in *Maximum Message Size* allow you to set a maximum size limit for processing inbound messages. Any inbound message that exceeds the configured limit is rejected from further processing and the sender receives an error message.

</td>
</tr>
<tr>
<td valign="top">

*Body Size \(in MB\)* 

</td>
<td valign="top">

Define the size limit for processing the message body. Default value is 40 MB.

</td>
</tr>
<tr>
<td valign="top">

*Attachment Size \(in MB\)* 

</td>
<td valign="top">

Define the size limit for processing the attachment. Default value is 100 MB.

</td>
</tr>
</table>

