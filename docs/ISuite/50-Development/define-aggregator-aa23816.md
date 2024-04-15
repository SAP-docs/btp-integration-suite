<!-- loioaa238166757b4f11878c50b07eb8b4b9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Aggregator



## Prerequisites

> ### Caution:  
> Usage of an Aggregator step in a Local Integration Process or Exception Subprocess is not supported.



## Context

You want to combine related individual messages so that they can be processed in bulk. Using an Aggregator pattern, you can collect and store individual messages until a complete set of related messages has been received. The aggregated message is then sent to the actual receiver. The message is retried every 5 minutes until it is successfully completed. To abort the retry processing you can handle the error in the Exception Subprocess ending in an End Event.

> ### Note:  
> When you use the Aggregator step in combination with a polling SFTP sender adapter and you expect a high message load, please consider the following recommendation:
> 
> For the involved in SFTP sender adapter set the value for *Maximum Messages per Poll* to a small number which is larger than 0 \(for example, `20`\) \(under *Advanced Parameters*\). That way, you ensure a proper message processing status logging at runtime.



## Procedure

1.  In the palette, choose *Message Routing*<span class="SAP-icons-V5"></span>, then choose** \> *Aggregator*.

2.  Place *Aggregator* in the integration process and define the message path.

3.  Specify the attributes of the aggregator.

    ****


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Correlation Expression \(XPath\)*
    
    </td>
    <td valign="top">
    
    XPath expression that identifies an element based on which the incoming messages should be correlated.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Incoming Format* 
    
    </td>
    <td valign="top">
    
    Content type of the incoming message

    Currently, only `XML (Same Format)` can be selected.

    It is important that the incoming messages have the same format.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Aggregation Algorithm* 
    
    </td>
    <td valign="top">
    
    Specifies how the correlated messages should be treated.

    You can select one of the following options:

    -   *Combine in Sequence* 

        Aggregated message contains all correlated incoming messages, and the original messages are put into a sequence.

    -   *Combine* 

        Aggregated message contains all correlated incoming messages.


    The *Aggregator* step generates an SAP Process Integration **multi mapping** as specific format. This is important to know because the integration developer typically has to create a mapping from the generated format to the message structure required by the receiver.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Message Sequence Expression \(XPath\)*

    \(only if for *Aggregation Algorithm* the option *Combine in Sequence* has been selected\)
    
    </td>
    <td valign="top">
    
    Enter an XPath expression for that message element based on which a sequence is being defined.

    You can use only numbers to define a sequence. Each sequence starts with `1`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Message Condition \(XPath\)* 
    
    </td>
    <td valign="top">
    
    Define the condition \(<code><code>XPATH</code> = <code>value</code></code>\) to identify the last message of an aggregate.

    You have the option to use an *Router* step after the *Aggregator* in order to evaluate the `Camel ${header.CamelAggregatedCompletedBy}` attribute, and, based on the value, decide how to continue.

    Note that the header attribute can only have one of the following values:

    -   `timeout`

        Processing of the aggregate has been finished because the configured *Completion Timeout* has been reached.

    -   `predicate`

        Processing of the aggregate has been finished because the *Completion Condition* has been fulfilled.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Completion Timeout* 
    
    </td>
    <td valign="top">
    
    Defines the maximum time between two messages before aggregation is being stopped \(*period of inactivity*\).

    You have the option to use an *Router* step after the *Aggregator* in order to evaluate the `Camel ${header.CamelAggregatedCompletedBy}` attribute, and, based on the value, decide how to continue.

    Note that the header attribute can only have one of the following values:

    -   `timeout`

        Processing of the aggregate has been finished because the configured *Completion Timeout* has been reached.

    -   `predicate`

        Processing of the aggregate has been finished because the *Completion Condition* has been fulfilled.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Store Name* 
    
    </td>
    <td valign="top">
    
    Enter the name of the transient data store where the aggregated message is to be stored. The name should begin with a letter and use characters \(aA-zZ, 0-9, - \_ . ~ \).

    Note that only **local** data stores \(that apply only to the integration flow\) can be used. Global data stores cannot be used for this purpose.

    > ### Note:  
    > The *Monitor* section provides a Data Store Viewer that allows you to monitor your transient data stores.


    
    </td>
    </tr>
    </table>
    
4.  Save the configuration.




<a name="loioaa238166757b4f11878c50b07eb8b4b9__postreq_bfp_h3n_l1b"/>

## Next Steps

The following header are supported by this step:

-   AggregatedCompletedBy

    This header is relevant for use cases with message aggregation.

    The header attribute can only have one of the following values:

    -   timeout

        Processing of the aggregate has been stopped because the configured Completion Timeout has been reached.

    -   predicate

        Processing of the aggregate has finished because the Completion Condition has been met.


-   AggregateCorrelationId

    -   Contains the value of the correlation expression evaluation.


-   AggregationSequenceNumber

    -   Contains the retreived sequence number.


-   AggregationIsLastMessage

    -   Boolean; true if it's the last message.



**Related Information**  


[Aggregator](aggregator-5f5e01b.md "You want to combine related individual messages so that they can be processed in bulk. Using an Aggregator pattern, you can collect and store individual messages until a complete set of related messages has been received. The aggregated message is then sent to the actual receiver.")

