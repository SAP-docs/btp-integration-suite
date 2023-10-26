<!-- loio5d8c0e64a12e4bfc866c17abf65936c2 -->

# AzureStorage Sender Adapter for Queue Storage

The AzureStorage sender adapter enables SAP Integration Suite to receive files from queues on Azure Storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the *AzureStorage* sender adapter and the *Queue Storage* message protocol, you can configure the following attributes.

Select the *General* tab to access the following parameters.

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
<tr>
<td valign="top">

*Direction* 

</td>
<td valign="top">

Sender

</td>
</tr>
<tr>
<td valign="top">

*System* 

</td>
<td valign="top">

Sender

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

AzureStorage

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

HTTPS

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

*Queue Storage*

Shows the message protocol selected when creating the channel.

</td>
</tr>
</table>

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

*Authentication* 

</td>
<td valign="top">

Select authentication option to use to connect to Azure Storage server. There are the following options:

-   *SAS Token*

-   *Shared Access Key*




</td>
</tr>
<tr>
<td valign="top">

*Token Alias*

\(Only if for *Authentication* the option *SAS Token* is selected\)

</td>
<td valign="top">

Alias name of token used to communicate with Azure Storage.

</td>
</tr>
<tr>
<td valign="top">

*Key Alias*

\(Only if for *Authentication* the option *Shared Access Key* is selected\)

</td>
<td valign="top">

Alias name of key used to communicate with Azure Storage.

</td>
</tr>
<tr>
<td valign="top">

*Timeout* 

</td>
<td valign="top">

Maximum waiting time, in milliseconds, to contact Azure Storage while establishing a connection or performing a read operation \(default value: 60000\).

Setting a timeout is mandatory for both token and key aliases.

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

*Operation* 

</td>
<td valign="top">

There are the following options.

-   *Get Messages*

-   *Peek Messages*




</td>
</tr>
<tr>
<td valign="top">

*Storage Account Name*

\(for both operations of get messages and peek messages\)

</td>
<td valign="top">

Enter name of the storage account.

</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

\(for both operations of get messages and peek messages\)

</td>
<td valign="top">

Specifies the queue name to retrieve the message\(s\).

</td>
</tr>
<tr>
<td valign="top">

*Max. Number Of Messages*

\(for both operations of get messages and peek messages\)

</td>
<td valign="top">

The number of messages to peek from the queue up to a maximum of 32. If you do not specify the number of messages, only one message is retrieved.

</td>
</tr>
<tr>
<td valign="top">

*Consume all messages in single payload* 

</td>
<td valign="top">

Specifies that all the messages in the *Max. Number of Messages* are combined into single payload..

</td>
</tr>
<tr>
<td valign="top">

*Visibility Timeout \(in s\)*

\(Only if for *Operation* the option *Get Messages* is selected\)

</td>
<td valign="top">

Visibility timeout value in seconds, up to a maximum of 120 seconds.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing Operations* 

</td>
<td valign="top">

There are the following options::

-   *Keep Message and Process Again*

    Keeps message in the storage and reprocesses it as specified by the scheduler. If you choose this option, the message is processed with every message processing run, even if it hasn't been changed.

-   *Keep Message and Mark as Processed in Idempotent Repository*

    Prevents message from being consumed again within the configured duration. For that purpose, an idempotent database is activated with the configured persist duration.

    > ### Note:  
    > The idempotent repository contains information on blobs already been consumed from Azure Storage. It stores the blob names in a database to synchronize between multiple worker nodes and to prevent the blobs from being read again when the runtime node is restarted. Blob name entries are deleted by default after 90 days.

-   *Delete Message*

    Message is deleted from Azure Storage after it has been processed successfully.




</td>
</tr>
<tr>
<td valign="top">

*Persist Duration \(in Days\)*

\(Only if for *Post-Processing* the option *Keep Message and Mark as Processed in Idempotent Repository* is selected\)

</td>
<td valign="top">

Enter the time \(in days\), for which queue name is to be stored in idempotent repository to avoid processing again within the given duration \(default: 90 days\).

</td>
</tr>
<tr>
<td valign="top">

*Raise Exception on Post-Processing Failure*

\(Only if for *Post-Processing* the option *Keep Message and Mark as Processed in Idempotent Repository* is selected\)

</td>
<td valign="top">

Select this option to raise error in the message processing log if post processing fails.

Using this option, if post-processing fails, the message gets *Failed* status. Otherwise, the message gets status *Successful*. In both cases, the post-processing operation status is stored in message property log.

</td>
</tr>
<tr>
<td valign="top">

*Request Format* 

</td>
<td valign="top">

The following request formats are given:

-   *JSON*

-   *XML* 

-   *Default*




</td>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Select a request parameter.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Specify the value of the argument. You can also enter`${header.headername}` or `${property.propertyname}` to dynamically read the value from the message exchange.

</td>
</tr>
</table>



Select the *Scheduler* tab and provide values in the fields as follows. The scheduler helps you to download the blobs on regular intervals as per the timer:

**Scheduler**


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

*Schedule on Day* 

</td>
<td valign="top">

There are the following options:

-   *On Date*: Select the date of the scheduling day.

-   *On Time*: Set the time of scheduling.

-   *Every*: Set the polling interval for the Azure Storage sender adapter.

-   *Time Zone*: Set the time zone.




</td>
</tr>
<tr>
<td valign="top">

*Schedule to Recur* 

</td>
<td valign="top">

There are the following options:

-   *Daily*: Select if scheduling needs to recur daily.

-   *Weekly*: Select if scheduling needs to recur weekly.

-   *Monthly*: Select if scheduling needs to recur monthly.

-   *On Time*: Set the time of scheduling.

-   *Every*: Polling interval for the Azure Storage sender adapter.

-   *Time Zone*: Set the time zone.




</td>
</tr>
</table>



<a name="loio5d8c0e64a12e4bfc866c17abf65936c2__section_h43_dzh_3wb"/>

## Default Headers and Exchange Properties


<table>
<tr>
<th valign="top">

Sl No

</th>
<th valign="top">

Operation

</th>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

Get messages in queue

</td>
<td valign="top">

SAP\_AzureStorage\_DeliveryCount

</td>
<td valign="top">

Property

</td>
<td valign="top">

When a message is retrieved for the first time, its `DequeueCount` property is set to 1.

If it is not deleted and is subsequently retrieved again, the `DequeueCount` property is incremented.

</td>
</tr>
</table>

