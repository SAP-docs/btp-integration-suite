<!-- loiob0576a824cdf46868fcc70fd9e697f16 -->

# Content Modifier Basics



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

You can use the *Content Modifier* step to modify a message by adding additional data to it.

More precisely, this step type allows you to modify the content of the following three data containers during message processing:

-   *Message Header*

    You can add headers to the message, and edit and delete headers.

-   *Message Body*

    You can modify the message body part.

-   *Exchange Property*

    You can write data to the message exchange, and edit and delete the properties.


For example, you can retrieve the value of a particular element of the payload of an inbound message and write this value to the header of the message \(to make it available for subsequent processing steps\).

You need to specify additional parameters in the Content Modifier step to tell the integration runtime how exactly to access the data from the incoming message \(which is to be written to one of the three data containers above\).

Here's a simple example to show how this works: Let's say you want to write the value of the element `CustomerNumber` from an inbound XML message to the message header, to make it available for subsequent process steps.

In this case, you could configure the Content Modifier as follows:

On the *Message Header* tab of the Content Modifier, add a new entry. Specify *XPath* as the *Type* \(because you want to address the `CustomerNumber` element in an incoming XML message\). For *Value*, enter the exact XPath expression that is to be used to address this element \(for example, */Order/Customer/CustomerNumber*\). In an additional field, you now need to specify the data format expected for the content of the `CustomerNumber` element. To express that this is a String element, you need to specify a valid Java data type, which is `java.lang.string` in this case. For *Name*, enter the desired name of the message header \(which should contain the `CustomerNumber` value\), for example, `CustomerNo`.



<a name="loiob0576a824cdf46868fcc70fd9e697f16__section_dbs_hzq_b1c"/>

## Example

The following example shows how to modify both the header and body data container of a message using the Content Modifier step.

Suppose that the incoming message has the following information:

```
<order>
	<book>
		<BookID>A1000</BookID>
		<Count>5</Count>
	</book>
</order>

```

On the *Message Header* tab of the Content Modifier, enter the following to write constant values to the message header:

****


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Name

</th>
<th valign="top">

Source Type

</th>
<th valign="top">

Source Value

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

vendor

</td>
<td valign="top">

constant

</td>
<td valign="top">

ABC Corp

</td>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

delivery date

</td>
<td valign="top">

constant

</td>
<td valign="top">

25062013

</td>
</tr>
</table>

On the *Body* tab, keep placeholders for the header information specified in the first Content Modifier step \(`${header.vendor}` and `${header.date}`\) to modify the content as shown below. Additionally, use a placeholder `${in.body}` for the incoming message.

```
<invoice>
<vendor>${header.vendor}</vendor>
${in.body}
<deliverydate>${header.delivery date}</delivery>
</invoice>

```

The output message would look like this:

```
<invoice>
<vendor>ABC Corp</vendor>
<order>
	<book>
		<BookID>A1000</BookID>
		<Count>5</Count>
	</book>
</order>
<deliverydate>25062013</deliverydate>
</invoice>

```

