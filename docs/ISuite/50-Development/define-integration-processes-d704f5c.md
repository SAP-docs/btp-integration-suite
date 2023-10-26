<!-- loiod704f5cafb194f059198656d8a1b4c6a -->

# Define Integration Processes

You use an Integration Process to define the steps to process the message transfer between the sender and receiver systems.

An integration flow template contains the following shapes: *Sender* \(this represents your sender system\), *Receiver* \(this represents a receiver system\), and *Integration Process*. The Integration Process shape contains a Start event and an End event.

The following values are displayed in the *General* tab.

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

If you want to provide a name for the integration process, enter a name here. The default is set to *Integration Process*.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Transaction Management**


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

*Transaction Handling* 

</td>
<td valign="top">

Select the relevant transactional database processing:

-   Required for JDBC

-   Required for JMS

-   Not Required


> ### Note:  
> See [Defining Transaction Handling](define-transaction-handling-2a5d4bc.md) for more information.



</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in min\)* \(only if *Required for JDBC* or *Required for JMS* is selected in *Transaction Handling*\)

</td>
<td valign="top">

Enter the time in minutes.

> ### Note:  
> This value refers to the transaction itself \(for example, data base operations\). The timeout will only terminate processes referenced in the transaction, not any other operations that are part of the integration flow.



</td>
</tr>
</table>

