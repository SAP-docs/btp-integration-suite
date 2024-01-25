<!-- loio31efe35bdf65422a8df18a08c4e4160f -->

# Data Storages

Cloud Integration comes with the following data storage features.



<a name="loio31efe35bdf65422a8df18a08c4e4160f__section_w4d_jbk_vkb"/>

## Cloud Integration Data Storages

> ### Note:  
> For guidelines how to use these features during integration flow design, check out [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md).
> 
> For information on the size limits of each data storages both in the Neo and Cloud Foundry environment, see [What Is SAP Cloud Integration?](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/e12c09cc8e9b4574b092d8964b049ce6.html "Support end-to-end process integration through the exchange of messages.") :arrow_upper_right:


<table>
<tr>
<th valign="top">

Physical Database

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Main memory \(only available during the processing of an integration flow\)

</td>
<td valign="top">

During the processing of an integration flow, the system can write data to and read data from the main memory. In particular, we talk about data containers that come with the Camel data model \(see [The Camel Data Model in a Nutshell](the-camel-data-model-in-a-nutshell-d4f8f03.md)\).

The data is accessible from there as long as the processing of a message lasts. After message processing for an integration flow has finished, this data isn't available anymore.

Constraints:

-   Data only available as long as message processing lasts \(there's no persistence\)

-   Overall storage size for headers and properties restricted

-   No tenant storage capacity required


The following data containers are available:

-   Exchange \(where you can store properties\)

-   Message header

-   Message body


Cloud Integration can transfer message headers and the message body to remote components \(other integration flows or connected systems\). However, exchange properties exist within a dedicated data container that is only available as long as processing of a single integration flow lasts. This container is referred to as exchange.

> ### Note:  
> Exchange properties can't be transferred across integration flows.
> 
> Message headers and the message body can be shared with remote components or with other integration flows \(for example, using the ProcessDirect adapter\).

See [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md)

</td>
</tr>
<tr>
<td valign="top">

Tenant database

</td>
<td valign="top">

During the processing of an integration flow, Cloud IntegrationCloud Integration tenant. The database keeps the data for a restricted amount of time.

The database is associated with a subaccount of SAP BTP.

You can store the following data in the tenant database:

-   Global/local data store content \(retention period: up to 180 days; default: 30 days\)

-   Global/local variable \(retention period: 400 days\)

-   Data required at runtime when aggregating messages \(retention period: 60 min \(depends on configured timeout\); as soon as the data has been consumed successfully, it isn't available anymore in the data store\)

-   Message store content \(retention period: 30 days\)

-   Message processing log attachments

-   Partner Directory content \(retention period: No limitation\)


> ### Note:  
> To be more precise from a technical perspective, the following assets are stored in the SAP BTP object store:
> 
> -   Message processing log attachments
> 
> -   Message store content



</td>
</tr>
<tr>
<td valign="top">

JMS queues

</td>
<td valign="top">

To asynchronously decouple inbound and outbound processing, Cloud Integration can store messages in message queues and read from there \(using the JMS adapter\). can write data to and read data from a database that comes with the

As soon as the message has been consumed successfully, it isn't available anymore in the queue.

Constraints:

-   Limited storage capacity, but can be enhanced

    More information:

    [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/)

    In particular, there's a limit of 4 MB for storing headers and properties.

-   Store message body and header \(and, optionally, properties\)

-   Retention period: 90 days \(default\)

    can write data to and read data from a database that comes with theThe system deletes messages from the queue that weren't consumed within this period.

-   As soon as the message has been consumed successfully, it isn't available anymore in the queue.




</td>
</tr>
</table>



<a name="loio31efe35bdf65422a8df18a08c4e4160f__section_djk_2bh_3rb"/>

## Remote Data Storages

Cloud Integration also provides options to integrate various kinds of remote data storage systems:

-   Remote archiving system

    The monitoring application can store message processing logs \(MPLs\) in a remote archiving system.

-   Remote database system

    If you like to integrate a permanent data storage in your scenario, you can set up a remote database system and connect Cloud Integration to it using the JDBC adapter.

-   Remote Kafka server

    You can connect Cloud Integration to an external Kafka server via Kafka protocol. With the help of the Kafka sender adapter you can receive messages; with the help of the Kafka receiver adapter you can send messages to the Kafka server.

-   Remote message broker

    You can connect Cloud Integration to an external message broker. With the help of the AMQP sender adapter you can receive messages; with the help of the AMQP receiver adapter you can send messages to the message broker.


