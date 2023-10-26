<!-- loio7e766dd8c4bf41dd968836a9c5427e65 -->

# Variant: Timer-Initiated Scenario with External Data Source and Receiver

Get started with integration flow design with a simple integration flow that processes data from an external data source, started by a timer.



<a name="loio7e766dd8c4bf41dd968836a9c5427e65__section_mrt_xgz_rmb"/>

## Implementation

In this scenario, you access an OData API and get information about a product \(for a specific product ID\). The result is sent to the Generic Receiver integration flow and stored as data store entry.

See the *Modeling Basics - Timer-Initiated Scenario with External Data Source and Receiver* integration flow:

![](images/Learn_the_Basics_Variant_Timer-Initiated_with_External_Source_1a713b6.png)


<table>
<tr>
<th valign="top">

Integration Flow

</th>
<th valign="top">

Tasks

</th>
</tr>
<tr>
<td valign="top">

*Modeling Basics - Timer-Initiated Scenario with External Data Source and Receiver*

</td>
<td valign="top">

Performs the main business-related steps \(calling WebShop component\).

</td>
</tr>
<tr>
<td valign="top">

*Generic Receiver*

</td>
<td valign="top">

Creates a Data Store entry to represent the receiver system \(both in success and error cases\).

</td>
</tr>
</table>

To make it as easy as possible for you to develop this first integration flow, you don't need to configure any sender system. That saves the effort for you to set up a dedicated sender system and to connect it to SAP Integration Suite . Instead, message processing is triggered by a Timer event, and the inbound message payload is created within the integration flow, in a dedicated Content Modifier step.

Furthermore, you don't need to set up a complicated receiver system. This integration flow works with the *Generic Receiver* that creates a data store entry and stands in as a receiver system.

The example scenario works as follows:

After you've deployed the integration flow, the first Content Modifier *Define message body* creates a message with only 1 element, a `productIdentifier` \(to identify a product from the product catalog\). The actual value of the *productIdentifier*is hard-coded in this step. If you like to process the integration flow with another product identifier, you need to change the value in this step and redeploy the integration flow again. The requirement of this additional activity is a drawback that results from not using a dedicated sender system:

> ### Sample Code:  
> ```
> <root>
> <productIdentifier>HT-1080</productIdentifier>
> </root>
> ```

The 2nd Content Modifier *Define property* defines a message header that determines the Data Store name for the message to be stored by the Generic Receiver integration flow:


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

context

</td>
<td valign="top">

Constant

</td>
<td valign="top">

ModelingBasics-TimerInitiated

</td>
</tr>
</table>

It also creates an Exchange property \(which we also call `productIdentifier`\) and writes the actual value of the `productIdentifier` element into it. This property is used in the subsequent step.


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

productIdentifier

</td>
<td valign="top">

XPath

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

//productIdentifier

</td>
</tr>
</table>

The Request Reply step *Request product data* passes over the message to an external data source and retrieves data \(about products\) from there.

The external data source is represented by the lower WebShop shape.

The external data source supports the Open DataProtocol \(OData\). For our scenario, we use the ESPM WebShop, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. The demo application can be accessed at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html)

For the connection to the WebShop, an OData receiver channel is used. To query for exactly 1 product \(for the product identifier provided with the inbound message\), the header that has been created in the preceding Content Modifier is used.

The OData API provides the details of one specific product \(according to the product identifier provided with the inbound message\).

As a last step, the Generic Receiver writes the data to the Data Store.

You can then run the integration flow and monitor message processing as described under: [Run the Integration Flow and Monitor the Message Processing](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/82d62320472c44849dd22b28b43eaacb.html).

