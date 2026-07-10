<!-- loioe49dbee00fa549f78b863b9f0ab736d4 -->

# Elements of an Integration Flow

An integration flow allows you to specify how a message is processed on a tenant.



You can use integration flows to specify specific integration patterns like mapping or routing.

A graphical editor allows you, the **integration developer**, to model the message processing steps and specify in detail what happens to the message during processing.

In detail, you define the following aspects in an integration flow:

-   The senders and receivers of the message
-   How the senders and receivers are connected to the tenant \(adapters\)
-   The steps that define the message processing

The following figure provides a simplified and generalized representation of an integration flow.

![Linear graphic descripion from left to right: Sender tile with a Channel arrow to Step 1 which is inside the Integration Flow box. Step 1 is then linked by an arrow to Step 2 which is equally is linked to Step 3. Step 3 branch off three Channel arows out of the Integration Flow box. Each of the arrows has a Receiver tile at the end.](images/HCI_Integration_Flow_Elements_f77edf2.png)



### Senders and Receivers

You define a participant of an integration scenario as a **sender** or **receiver**. The senders and receivers typically represent the customer systems that are connected to the tenant and exchange messages with each other.



### Connectivity \(Adapters\)

An integration flow **channel** allows you to specify which technical protocols should be used to connect a sender or a receiver to the tenant.

> ### Note:  
> To specify an adapter, click the connection arrow between the sender/receiver and the Integration Process box.



### Message Processing \(Steps\)

You use integration flow steps to specify what should happen to a message during processing. Various step types support the wide range of **integration capabilities** of the Cloud-based integration platform.

> ### Note:  
> To insert a step into an integration flow, drag and drop the desired step type from the palette on the right of the graphical modeling area.



### Message Flows

You use message flows to connect various integration flow elements.



### 

**Related Information**  


[Configure Adapter in Communication Channels](configure-adapter-in-communication-channels-1f06633.md "")

