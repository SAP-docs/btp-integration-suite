<!-- loiod7fddbd52e3944d3a6d4e5b228c7e63b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Router



<a name="loiod7fddbd52e3944d3a6d4e5b228c7e63b__context_N10025_N10011_N10001"/>

## Context

You perform this task when you have to specify conditions based on which the messages are routed to a receiver or an interface during runtime. If the message contains XML payload, you form expressions using the XPath-supported operators. If the message contains non-XML payload, you form expressions using the operators shown in the following table:

**Usage of Operators in Non-XML Conditions**


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

=

</td>
<td valign="top">

$\{header.SenderId\} = '1'

</td>
</tr>
<tr>
<td valign="top">

!=

</td>
<td valign="top">

$\{header.SenderId\} != '1'

</td>
</tr>
<tr>
<td valign="top">

\>

</td>
<td valign="top">

$\{header.SenderId\} \> '1'

</td>
</tr>
<tr>
<td valign="top">

\>=

</td>
<td valign="top">

$\{header.SenderId\} \>= '1'

</td>
</tr>
<tr>
<td valign="top">

<

</td>
<td valign="top">

$\{header.SenderId\} < '1'

</td>
</tr>
<tr>
<td valign="top">

<=

</td>
<td valign="top">

$\{header.SenderId\} <= '1'

</td>
</tr>
<tr>
<td valign="top">

and

</td>
<td valign="top">

$\{header.SenderId\}= '1' and $\{header.ReceiverId\} = '2'

</td>
</tr>
<tr>
<td valign="top">

or

</td>
<td valign="top">

$\{header.SenderId\}= '1' or $\{header.ReceiverId\}= '2'

</td>
</tr>
<tr>
<td valign="top">

contains

</td>
<td valign="top">

$\{header.SenderId\} contains '1'

</td>
</tr>
<tr>
<td valign="top">

not contains

</td>
<td valign="top">

$\{header.SenderId\} not contains '1'

</td>
</tr>
<tr>
<td valign="top">

in

</td>
<td valign="top">

$\{header.SenderId\} in '1,2'

</td>
</tr>
<tr>
<td valign="top">

not in

</td>
<td valign="top">

$\{header.SenderId\} not in '1,2'

</td>
</tr>
<tr>
<td valign="top">

regex

</td>
<td valign="top">

$\{header.SenderId\} regex '1.\*'

</td>
</tr>
<tr>
<td valign="top">

not regex

</td>
<td valign="top">

$\{header.SenderId\} not regex '1.\*'

</td>
</tr>
</table>

> ### Example:  
> A condition with expression `${header.SenderId} regex '1.*'` routes all the messages that have a Sender ID starting with 1.

> ### Note:  
> -   You can define a condition based on property or exception that may occur.
> 
> -   If the condition `${property.SenderId} = '1'` is true, then Router routes the message to a particular sender whose Sender ID is 1.
> 
> -   If the condition `${exception.message}contains 'java.lang.Exception'` is true, then Router routes the message to a particular receiver, otherwise it routes to another receiver.



<a name="loiod7fddbd52e3944d3a6d4e5b228c7e63b__steps_qx4_pcg_vdb"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Router*.

2.  Place the *Router* element in the integration process and define the message path.

3.  Select either *Router* or the routing branch \(*Route*\) splitting from the router.

4.  If you select *Router*, then execute the following steps:

    1.  On the *General* tab, you can change the name of the *Router* element.

    2.  On the *Processing* tab, select *Throw Exception* to respond to an error occurence.

        You can also use *Error End Event* to raise an exception.

    3.  In the *Routing Condition* table, select the default route.

        If you select *Throw Exception*, the default route must terminate with *Terminate Message*.


5.  If you select *Route*, then execute the following steps.

    1.  On the *General* tab, you can change the name of the route.

    2.  On the *Processing* tab, from the *Expression Type* dropdown, select the type of expression used to formulate the routing condition.

    3.  Select *XML* to form an expression using XPath or select *Non-XML* to form an expression using message header, property, or exception.

    4.  In the *Condition* field, formulate a valid XML or non-XML condition that routes the message to its associated receiver.

        > ### Recommendation:  
        > We recommend that you ensure that the routing branches of a router are configured with the same type of condition, either XML or non-XML, and not a combination of both. At runtime, the specified conditions are executed in the same order. If the conditions are a combination of both non-XML and XML type, the evaluation fails.

    5.  If you want to set the selected route as the default, so that its associated receiver handles the error situation if no receiver is found, select the *Default Route* option.

        > ### Note:  
        > Only the route that you last selected as *Default Route* is considered the default route.


6.  Save or deploy the configuration.


