<!-- loiod4f8f033a62345caae6f3a7ce249390b -->

# The Camel Data Model in a Nutshell

An integration flow is a BPMN \(Business Process Model and Notation\)-like model that allows you to specify how a message is to be processed on a tenant.

To interpret an integration flow model at runtime, it is transformed into an XML structure that is compatible with Apache Camel \([http://camel.apache.org](http://camel.apache.org)\), an Open Source integration framework for Java that supports the mediation and routing of messages of any format.

The only prerequisite for a message that is to be processed by the Camel framework is that it comprises the following elements:

-   Headers

    Contain information related to the message, for example, information for addressing the message sender.

-   Attachments

    Contain optional data that is to be attached to the message.

-   Body

    Contains the payload \(usually with the business-related data\) to be transferred in the message.


For as long as a message is being processed, a data container \(referred to as *Exchange*\) is available. This container is used to store additional data besides the message that is to be processed. An Exchange can be seen as an abstraction of a message exchange process as it is executed by the Camel framework. An Exchange is identified uniquely by an Exchange ID. In the *Properties* area of the Exchange, additional data can be stored temporarily during message processing. This data is available for the runtime during the whole duration of the message exchange.

