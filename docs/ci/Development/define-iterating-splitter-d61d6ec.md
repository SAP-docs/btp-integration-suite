<!-- loiod61d6ecc8c8d453baa95c59e85f9cab1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Iterating Splitter



## Context

The Iterating Splitter splits a composite message into a series of smaller messages without copying the enveloping elements of the composite message \(see: [General and Iterating Splitter](general-and-iterating-splitter-b49d088.md)\).

If you use a Splitter step in a local integration process, the following limitations apply:

-   You can use Splitter and Gather steps together, but you must close each Splitter step with a Gather step.

-   You cannot use a Splitter without a child element.

-   If a Splitter is used in combination with Gather, the message returned to the main process is the message at the end of the local process.

-   If a Splitter is used in the local process with a step other than Gather, the message returned to the main process is the message before the Splitter step.

-   Combinations with other steps may behave unexpectedly.




## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Splitter* \> *Iterating Splitter*.

2.  Place the *Iterating Splitter* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Iterating Splitter* element.

4.  On the *Processing* tab, define the attributes of the element based on the descriptions in the following table.


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Token* \(Enabled only if you select *Token* in the *Expression Type* field\)
    
    </td>
    <td valign="top">
    
    The keyword or token to be used as a reference for splitting the composite message
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *XPath* 
    
    </td>
    <td valign="top">
    
    XPath to the split term.

    You can specify the absolute or relative path or a reference to a header property.

    > ### Note:  
    > Note that only the following types of XPath expressions are supported:
    > 
    > -   Absolute XPath expressions, for example, `/A/B/C/D`
    > 
    > -   Relative XPath expressions, for example, `//D` 
    > 
    > 
    > The following characters are **not** supported in an XPath expression:
    > 
    > |, +, \*, \>, <, \>=, <=, \[, \], @.

    > ### Caution:  
    > You cannot split by **values** of message elements.
    > 
    > Consider the following inbound message:
    > 
    > ```
    > <customerList>
    >     <customers>
    >         <customerNumber>0001</customerNumber>
    >         <customerName>Paul Smith</customerName>
    > 	</customers>
    >     <customers>
    >         <customerNumber>0002</customerNumber>
    >         <customerName>Seena Kumar</customerName>
    >     </customers>
    > </customerList>
    > 
    > ```
    > 
    > In that case, using the following XPath expression is **not** supported to split the message at the `customerNumber` node with the value `0001`:
    > 
    > `/customerList/customers/customerNumber=0001`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Grouping* 
    
    </td>
    <td valign="top">
    
    The size of the groups into which the composite message is to be split. You can also enter a reference to a header or property instead of a fixed value for Grouping.

    For example, if a message has 10 nodes and grouping is defined as 2, the message is split into 5 messages with 2 nodes each.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Streaming* 
    
    </td>
    <td valign="top">
    
    Select this option if you want to stream the process of splitting a large composite message.

    If you activate streaming, the system already starts processing parts \(*chunks*\) of the composite message before the message is fully transferred to the memory \(of the runtime node\).

    If you deactivate this option, the message is transferred fully to the memory before it is split and processed further. Deactivating streaming is more memory-intensive than activating it.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parallel Processing* 
    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to enable processing of all the split messages at once.

    More information: [Cloud Integration – Using Parallel Processing in General and Iterating Splitter](https://blogs.sap.com/2018/10/17/cloud-integration-using-parallel-processing-in-general-and-iterating-splitter/) \(SAP Community blog\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Number of Concurrent Processes*

    \(Enabled only if *Parallel Processing* is selected\)
    
    </td>
    <td valign="top">
    
    If you have selected *Parallel Processing*, the split messages are processed concurrently in threads. Define how many concurrent processes to use in the splitter. The default is 10. The maximum value allowed is 50.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Timeout \(in s\)*

    \(Enabled only if *Parallel Processing* is selected\)
    
    </td>
    <td valign="top">
    
    Maximum time in seconds that the system waits for processing all split items to complete before it is aborted. The default value is 300 seconds.

    > ### Caution:  
    > If the overall processing takes longer than the specified time, the splitter operation stops without exception, and the next elements in the integration flow sequence are processed.
    > 
    > This behavior can lead to unexpected results \(even data loss\) if not all message splits are processed within the timeout period.
    > 
    > In particular, if you are using a *Gather* step in combination with the *Splitter*, there's the risk that your output is incomplete.

    > ### Tip:  
    > **Example**
    > 
    > You've designed a *Splitter* step in combination with a closing *Gather* step.
    > 
    > The inbound payload contains 100 items to split, and you've activated *Parallel Processing* with the following settings:
    > 
    > -   *Number of Concurrent Processes*: `10`
    > 
    > -   *Timeout \(in s\)*: `60` \(1 minute\)
    > 
    > 
    > Let's assume that after 1 minute 10 of the 100 elements have been fully processed and there are further 10 elements in processing.
    > 
    > The *Parallel Processing* settings affect message processing in the following way:
    > 
    > -   The 10 fully processed messages are used in the *Gather* step to create the final, merged message.
    > 
    > -   Processing of the 10 elements that are currently in processing continues until processing is finished.
    > 
    >     However, these 10 messages are used in the *Gather* step.
    > 
    > -   The remaining 80 messages are ignored.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Stop On Exception* 
    
    </td>
    <td valign="top">
    
    Select this option to stop message processing if an exception occurs.
    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.




## Next Steps

When a message is split \(as configured in a Splitter step of an integration flow\), the Camel headers listed below are generated every time the runtime finishes splitting an Exchange. You have several options for accessing these Camel headers at runtime. For example, suppose that you are configuring an integration flow with a Splitter step before an SFTP receiver adapter. If you enter the string `split_${exchangeId}_Index${property.CamelSplitIndex}` for *File Name*, the file name of the generated file on the SFTP server contains the property `CamelSplitIndex`. This property contains the information on the number of split Exchanges induced by the Splitter step.

-   CamelSplitIndex

    Provides a counter for split items that increases for each Exchange that is split \(starts from 0\).

-   CamelSplitSize

    Provides the total number of split items \(if you are using stream-based splitting, this header is only provided for the last item, in other words, for the completed Exchange\).

-   CamelSplitComplete

    Indicates whether an Exchange is the last split.


**Related Information**  


[General and Iterating Splitter](general-and-iterating-splitter-b49d088.md "The two splitter types General Splitter and Iterative Splitter behave differently in their handling of the enveloping elements of the input message.")

[General and Iterating Splitter \(Examples\)](general-and-iterating-splitter-examples-698e594.md "")

[“Stop on Exception” for Iterating/General Splitter | SAP Blogs](https://blogs.sap.com/2018/01/16/stop-on-exception-for-iteratinggeneral-splitter/)

[“Grouping” Option of Iterating/General Splitter | SAP Blogs](https://blogs.sap.com/2018/01/26/grouping-option-of-iteratinggeneral-splitter/)

[Cloud Integration – Usage of Splitter Flow Steps in Local Process | SAP Blogs](https://blogs.sap.com/2018/02/07/cloud-integration-usage-of-splitter-flow-steps-in-local-process/)

[Cloud Integration – Usage of General and Iterating Splitter with Exception Handling | SAP Blogs](https://blogs.sap.com/2018/10/17/cloud-integration-usage-of-general-and-iterating-splitter-with-exception-handling/)

[Cloud Integration – Using Parallel Processing in General and Iterating Splitter | SAP Blogs](https://blogs.sap.com/2018/10/17/cloud-integration-using-parallel-processing-in-general-and-iterating-splitter/)

