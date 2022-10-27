<!-- loio5b387653ddb14795b9407ebbf471c1cf -->

# Anticipate Message Throughput When Choosing a Storage Option

Make sure to anticipate the message throughput per time interval when deciding which storage best fits the requirements of a certain integration flow.

Cloud Integration is, first and foremost, designed as a *data in transit* message broker that can receive, process, and forward messages. It isn't designed primarily as a database application.

However, many business processes require you to store data on the SAP Integration Suite tenant. SAP Cloud Integration offers various logical storages for that purpose.

-   You can temporarily store message content in data storages on the tenant database or in JMS queues.

    There are the following logical data storages:

    -   Global/local data store entries

    -   Global/local variables

    -   Messages stored in JMS queues

    -   Partner Directory content


    Data stored in these storage locations can be shared across different steps of an integration flow or across multiple integration flows \(deployed on the same tenant\). Storing such data requires space on the tenant database \(which is limited\).

    Temporarily storage means that the data is deleted after a certain retention time. To calculate the expected data volume when using such data storage options, you need to consider the expected message sizes, the numbers of steps where data is stored, and the retention times.

    More information about the retention times:

    [Specific Data Assets](../60-Security/specific-data-assets-0e4e511.md) 

    > ### Note:  
    > There's also the option to use SAP Integration Suite together with a permanent data storage option. Such a data storage can be used through the JDBC adapter \(see: [JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md)\). Note that, however, using these permanent data storage options doesn't affect the storage capacity of your tenant. Therefore, these options aren't object of this discussion.

-   You can use the data container provided by the Camel data model as long as a message processing takes place.

    More information: [The Camel Data Model in a Nutshell](the-camel-data-model-in-a-nutshell-d4f8f03.md)

    During the processing of a message, you can hold data in the following data containers:

    -   Message body \(containing typically the business content\) and message header

        Data contained in the message body or the message header can be passed on from 1 integration flow to another one \(either deployed on the same or another tenant\). However, during the processing of an integration flow, the message body and message headers can get lost, in particular, during a step that calls another component through a receiver adapter.

    -   Exchange properties

        During a message processing run, you can store a certain value \(for example, a timestamp\) in an exchange property and access this value at a later step within the same Camel exchange. In general, the data stored in the exchange container is available as long as 1 integration flow is being processed. Therefore, exchange properties cannot be shared across different integration flows \(the exchange container is open only as long as processing takes place\). However, for certain integration patterns also during the processing of a single integration flow multiple exchanges are active. This is the case, for example, when you use the Multicast pattern. For each branch of a multicast scenario, a separate exchange is opened. In such a case, sharing properties across different exchanges opened within the course of the same integration flow isn't possible.



There are many cases where you need to access these data containers/storages, namely when you need to parameterize integration flows.

> ### Note:  
> SAP Integration Suite comes with more data storage features not covered in this section. Namely, you can connect your SAP Integration Suite tenant to remote database systems, archiving systems, or message brokers.
> 
> For a detailed overview, refer to [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md).



<a name="loio5b387653ddb14795b9407ebbf471c1cf__section_axx_3vj_vkb"/>

## Use Cases

A common use case is that data needs to be shared across different integration flows or across different steps within the same integration flow. For example, you need to set a timestamp at a certain step and access this value in a subsequent step or in another integration flow.

**General Recommendation**

-   If data is to be shared across different integration flows, prefer using headers \(instead of global variables or data store entries\) whenever possible. This option isn't at the expense of the tenant's storage capacity.

    However, this option is not available when integration flows are operated independently from each other, as described under [Variant: Sharing Data Across Integration Flows That Operate Independently from Each Other](variant-sharing-data-across-integration-flows-that-operate-independently-from-each-other-1459948.md). In this case, you have to use Variables or the data store.

-   If data is to be shared across different steps of 1 integration flow, use exchange properties whenever possible. The reason is that message headers can be deleted at various steps within an integration flow \(namely, when external systems or other integration flows are called\). Assuming the integration flow receives a certain value in a message header and this value is required at a later step in the integration flow. In this case, store the header value as exchange property so that it can be accessed to at a later step in the integration flow.

-   If you rely on using the tenant database \(using local/global data store entries or local/global variables\), consider the following difference between both options:

    Data store operations always use the payload of the message \(and, if specified, also the header\). If you like to share only a single value such like a timestamp or the value of a certain payload element, using a local/global variable is recommended.


> ### Tip:  
> For a complete overview of the data storage features and the use cases, refer to [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md).
> 
> For an overview of the technical details and limitations of each data storage option features, see [Data Storages](data-storages-31efe35.md).

Furthermore, more specific rules can be given depending on which of the following variant you plan to implement:

-   [Variant: Sharing Data Within the Same Integration Flow](variant-sharing-data-within-the-same-integration-flow-4b75ded.md)

-   [Variant: Sharing Data Across Integration Flows That Communicate with Each Other](variant-sharing-data-across-integration-flows-that-communicate-with-each-other-fe6d139.md)

-   [Variant: Sharing Data Across Integration Flows That Operate Independently from Each Other](variant-sharing-data-across-integration-flows-that-operate-independently-from-each-other-1459948.md)


For guidelines and use cases for JMS queues \(compared to data store/variables\), refer to: [Data Store, Variables, and JMS Queues: When to Use Which Option?](data-store-variables-and-jms-queues-when-to-use-which-option-6bc21cb.md).

