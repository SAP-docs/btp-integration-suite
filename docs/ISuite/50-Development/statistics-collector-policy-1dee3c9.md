<!-- loio1dee3c936b744e9897233bb5d757cf28 -->

# Statistics Collector Policy

This policy enables you to collect statistics for data in a message, such as product ID, price, REST action, client and target URL, and message length.

The data comes from flow variables predefined by API Management or custom variables that you define. The statistics data is passed to the analytics server, which analyzes the statistics and generates reports. This can be viewed by creating custom charts.

Only one Statistics Collector policy should be attached to a single API proxy. If there are multiple Statistics Collector policies in a proxy, then the last one to execute determines the data written to the analytics server. You can attach the policy in one of the following locations:

![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy collects data for each request and passes to the analytics server, in the below policy, 
> the data is colleted from productID and the price variables. if the variables are not set, the default values are used -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <StatisticsCollector xmlns="http://www.sap.com/apimgmt">
>     <Statistics>
>         <Statistic name="productID" ref="product.id" type="string">999999</Statistic>
>         <Statistic name="price" ref="product.price" type="string">0</Statistic>
>     </Statistics>
> </StatisticsCollector>
> ```


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

The name used to reference the data collected for the specified variable. When viewing analytics data, use this name to reference the data collected about the variable specified by the ref attribute. If the variable specified by ref is undefined on a request or response, then defaultStatValue specifies the value collected for the variable. If you omit the default value, no data is collected for the variable when the variable is undefined. The following restrictions apply:

-   Names cannot be multiple-word \(no spaces\).

-   No spaces, m dashes, quotation marks, underscores, hyphens, or periods.
-   No special characters.



</td>
</tr>
<tr>
<td valign="top">

ref

</td>
<td valign="top">

The flow variable for which you are collecting statistics. This variable can be a flow variable predefined by API Management or a custom variable that you define in your API proxy. The ref attribute often references a custom variable defined by the Extract Variables policy.

</td>
</tr>
<tr>
<td valign="top">

type

</td>
<td valign="top">

Specifies the data type of the variable specified by the ref attribute. Valid values are: string/integer/float/long/double. For data of type string, reference the statistical data as a Dimension in a custom report. For numerical data types \(integer/float/long/double\), reference the statistical data in a custom report as a Metric. See Create custom reports for more. The value of type can be omitted only if ref refers to a predefined API Management flow variable or the type is declared in the XML payload of the Extract Variables policy.

</td>
</tr>
<tr>
<td valign="top">

Default Value

</td>
<td valign="top">

If you omit this element, the value of the policy's name attribute is used.

</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Code**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Fault String

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

UnsupportedDatatype

</td>
<td valign="top">

StatisticsCollection \[collection\]: Datatype \[type\] is unsupported . Context \[context\]

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

InvalidName

</td>
<td valign="top">

StatisticsCollection: Name: \[name\] conflicts with system defined variables. Context \[context\]

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

DatatypeMissing

</td>
<td valign="top">

StatisticsCollection \[name\]: Datatype of \[type\] is missing. Context \[context\]

</td>
<td valign="top">

See the fault string.

</td>
</tr>
</table>

