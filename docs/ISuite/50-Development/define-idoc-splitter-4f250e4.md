<!-- loio4f250e48ba404724a7741c6c24e37983 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define IDoc Splitter

This step splits a composite IDoc message into a series of individual IDoc messages. Each individual message contains the enveloping elements of the composite IDoc message.



## Context

Make sure that you use this step only in combination with an IDoc receiver adapter that sends a request for each individual IDoc message to the receiver system.

The response from the receiver system contains a number of headers.


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`SapIDocAssignMap`

</td>
<td valign="top">

Contains a list of all `SapIDocTransferId` and `SapIDocDbId` headers that were returned from the IDoc receiver adapter for the splitted IDoc message.

</td>
</tr>
<tr>
<td valign="top">

`SapIDocTransferId`

</td>
<td valign="top">

Contains transfer ID of the original IDoc message.

This header contains the incoming IDoc number from the sending system \(for example, 0000000000166099\).

It corresponds to the field DOCNUM in the IDoc adapter.

</td>
</tr>
<tr>
<td valign="top">

`SapIDocDbId`

</td>
<td valign="top">

Contains db ID of the original IDoc message.

The IDoc receiver adapter sends a request and gets an XML response.

The adapter parses the XML response and generates this header from it. The header contains the IDoc number from the receiver system \(for example, 0000000000160816\).

</td>
</tr>
</table>



<a name="loio4f250e48ba404724a7741c6c24e37983__steps_x3x_zqz_1lb"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Splitter* \> *IDoc Splitter*.

2.  Place the *IDoc Splitter* element in the integration process and define the message path.

    No parameters are to be configured for this step.

    > ### Note:  
    > This step works in the same way like a General Splitter with an XPath Expression set to `//IDOC`.

3.  Save or deploy the configuration.




## Example

The IDoc splitter splits a composite IDoc message at the element `IDoc` \(split point\).

Assume that the inbound IDoc message to be processed by the IDoc splitter has the following structure.

> ### Sample Code:  
> ```
> <WPDTAX01>
> 		<IDOC BEGIN="1">
> 			<EDI_DC40 SEGMENT="1">
> 				<TABNAM>EDI_DC40</TABNAM>
> 				<MANDT>100</MANDT>
> 				<DOCNUM>0001</DOCNUM>
> 				...
> 			</EDI_DC40>
> 			<E1WPT01 SEGMENT="1">
> 				<FILIALE>Walldorf</FILIALE>
> 				<AENDKENNZ>123</AENDKENNZ>
> 				...
> 			</E1WPT01>
> 		</IDOC>
> 		<IDOC BEGIN="1">
> 			<EDI_DC40 SEGMENT="1">
> 				<TABNAM>EDI_DC40</TABNAM>
> 				<MANDT>100</MANDT>
> 				<DOCNUM>0002</DOCNUM>
> 				...
> 			</EDI_DC40>
> 			<E1WPT01 SEGMENT="1">
> 				<FILIALE>Walldorf</FILIALE>
> 				<AENDKENNZ>123</AENDKENNZ>
> 				...
> 			</E1WPT01>
> 		</IDOC>
> 	</WPDTAX01>
> ```

This message is split into the following individual messages.

The structure of the first message is:

```
<WPDTAX01>
		<IDOC BEGIN="1">
			<EDI_DC40 SEGMENT="1">
				<TABNAM>EDI_DC40</TABNAM>
				<MANDT>100</MANDT>
				<DOCNUM>0001</DOCNUM>
				...
			</EDI_DC40>
			<E1WPT01 SEGMENT="1">
				<FILIALE>Walldorf</FILIALE>
				<AENDKENNZ>123</AENDKENNZ>
				...
			</E1WPT01>
		</IDOC>

	</WPDTAX01>
```

The structure of the second message is:

```
<WPDTAX01>

		<IDOC BEGIN="1">
			<EDI_DC40 SEGMENT="1">
				<TABNAM>EDI_DC40</TABNAM>
				<MANDT>100</MANDT>
				<DOCNUM>0002</DOCNUM>
				...
			</EDI_DC40>
			<E1WPT01 SEGMENT="1">
				<FILIALE>Walldorf</FILIALE>
				<AENDKENNZ>123</AENDKENNZ>
				...
			</E1WPT01>
		</IDOC>
	</WPDTAX01>
```

**Related Information**  


[Configure the IDoc Receiver Adapter](configure-the-idoc-receiver-adapter-018aa88.md "The IDoc receiver adapter enables SAP Integration Suite to send Intermediate Document (IDoc) messages to a receiver.")

