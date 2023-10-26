<!-- loio4eac8a76385e47e99c64b8bf15d18a8d -->

# Variant 3: Splitter with Gather with Stop on Exception and with Exception Subprocess

The example integration flow *Handle Errors - Splitter Gather with Stop on Exception* is designed in the following way.

![](images/Splitter_Gather_with_Stop_on_Exception_cd0589a.png)

This example scenario works in the following way:

1.  SAP Cloud Integration receives a composite \(bulk\) message through an HTTPS adapter.

    The bulk message contains a purchase order with multiple items.

2.  The Splitter step divides the bulk message into as many individual messages as there are order items.

    The following settings have been defined for the Splitter step:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Expression Type
    
    </td>
    <td valign="top">
    
    XPath
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XPath Expression
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Items/Item
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Grouping
    
    </td>
    <td valign="top">
    
    1
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Stop on Exception
    
    </td>
    <td valign="top">
    
    \(Selected\)
    
    </td>
    </tr>
    </table>
    
3.  The individual messages are processed in a separate Local Integration Process. In the example scenario, a simple message mapping transforms the `Item``Item` node of the target structure.

4.  A Filter step removes header information that is duplicated for each split message.

5.  A Gather step combines all message chunks.

    The following aggregation strategy has been defined for the Gather step:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Incoming Format
    
    </td>
    <td valign="top">
    
    XML \(Same Format\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Aggregation Algorithm
    
    </td>
    <td valign="top">
    
    Combine
    
    </td>
    </tr>
    </table>
    
6.  A Content Modifier combines all pieces \(header and items\).

7.  The resulting message is sent to the receiver.


Dedicated elements in the integration flow model have dedicated tasks:


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*Integration Process: Message Splitter with Stop on Exception*

</td>
<td valign="top">

Main integration flow

</td>
</tr>
<tr>
<td valign="top">

*Local Integration Process: Split Process*

</td>
<td valign="top">

Local integration flow encapsulating split logic

</td>
</tr>
<tr>
<td valign="top">

*Exception* \(Receiver shape\)

</td>
<td valign="top">

Generic Receiver integration flow creating a Data Store entry in error case.

</td>
</tr>
<tr>
<td valign="top">

*Receiver1* \(Receiver shape\)

</td>
<td valign="top">

Generic Receiver integration flow creating a Data Store entry to represent the receiver system in success case.

</td>
</tr>
</table>

Errors occurring in the split processing are handled in an Exception Subprocess in the local split process. In the Exception Subprocess, an entry to data store is written as simple error handling. The Exception Subprocess ends with an Error End event. 

If an error occurs, processing ends because the *Stop on Exception* option is enabled for the Splitter. The next split is not executed. The message gets a *Failed* status in the monitoring.



<a name="loio4eac8a76385e47e99c64b8bf15d18a8d__section_h34_g3b_hlb"/>

## Executing the Scenario

To run this scenario, open folder *SplitterWithExceptionSubprocess* of the Postman collection.

Select one of the following requests:

-   *SplitterGatherWithStopOnException\_withError*

    To simulate an error situation, run the integration flow with this request. The processing stops because of an invalid price of one of the purchase order items \(in the request payload\). Due to the invalid price, message mapping fails.

     node of the source structure toWhen monitoring the message processing, the integration flow has status *Failed*.

-   *SplitterGatherWithStopOnException\_withoutError*

    To simulate successful message processing, run the integration flow with this request.




<a name="loio4eac8a76385e47e99c64b8bf15d18a8d__section_nv3_d3f_plb"/>

## Expected Behavior

If message processing is successful, in the Monitor application you find the following entries:

-   1 entry in Data Store *MessageGather-successful* \(all items aggregated\)

    2 new message processing logs in *Completed* state, 1 for integration flow *Handle Errors - Splitter Gather with Stop on Exception* \(related to the guideline\) and 1 for the *GenericReceiver* integration flow.


In the error case, in the Monitor application you find the following entries:

-   1 entry in Data Store *MessageSplitter\_exception* \(item 40\)

-   1 message processing log for integration flow *Handle Errors - Splitter Gather with Stop on Exception* \(related to the guideline\) in *Failed* state

-   1 message processing log for the *GenericReceiver* integration flow in *Completed* state


