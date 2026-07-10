<!-- loio0974c4f3c9304694a66bcb77dc275c64 -->

# About Headers and Exchange Properties



The integration framework gives you options to evaluate certain parameters at runtime, which allows you to define sophisticated ways of controlling message processing. There are two different kinds of parameter:

-   Message header

    This is transferred as part of the message header.

    When you use an HTTP-based receiver adapter, these parameters are converted to HTTP headers and transferred as such to the receiver.

    > ### Note:  
    > Note that data written to the message header during a processing step, for example, in a Content Modifier or Script step, also becomes part of the outbound message addressed to a receiver system. However, properties remain within the integration flow and are not handed over to receivers. Because of this, it is important to consider the following header size restriction if you are using an HTTP-based receiver adapter: If the message header exceeds a certain value, the receiver may not be able to accept the inbound call. This rule applies to all HTTP-based receiver adapters. The limiting value depends on the characteristics of the receiver system, but typically ranges between 4 and 16 KB. To overcome this issue, you can use a subsequent Content Modifier step to delete all headers that are not supposed to be part of the outbound message.

-   Exchange property

    For as long as a message is being processed, a data container \(referred to as *Exchange*\) is available. This container is used to store additional data besides the message that is to be processed. An Exchange can be seen as an abstraction of a message exchange process as it is executed by the Camel framework. An Exchange is identified uniquely by an Exchange ID. In the *Properties* area of the Exchange, additional data can be stored temporarily during message processing. This data is available for the runtime during the whole duration of the message exchange.

    When you use an HTTP-based receiver adapter, Exchange properties are **not** converted to an HTTP header for transfer to the receiver.


You can use the Content Modifier to modify the content of the message header and the Exchange property \(as well as of the message body\) at one or more steps during message processing.

You can use the message header and the Exchange property to configure various sophisticated ways of controlling message processing.

One option is to use dynamic parameters:

When configuring an integration flow using the modeling user interface, you can define placeholders for attributes of certain adapters or step types. The value that is actually used for message processing is set dynamically based on the content of the message. You can use a certain message header or Exchange property to dynamically set a specific integration flow property.

Another option to derive such data from a message at runtime is to access a certain element in the message payload.

> ### Note:  
> A subset of these parameters is provided by the associated Open Source components, such as Apache Camel.

**Related Information**  


[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

