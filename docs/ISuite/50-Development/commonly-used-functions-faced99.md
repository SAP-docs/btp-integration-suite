<!-- loiofaced99124b545c48bff31c583f1d8cc -->

# Commonly Used Functions

When designing integration content, you come across common questions such like how to get the current system time \(for example\). The following table explains how to solve such common problems.


<table>
<tr>
<th valign="top">

How to ...

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Get current system time

</td>
<td valign="top">

Use the following expression:

`${date:now:yyyy-MM-dd HH:mm:ss}`

The following blog shows how to store the system time as variable \(to make it available for another integration flow on the same tenant\): [Cloud Integration – Using the JDBC Adapter to Implement a Robust Scenario that Handles an Exception](https://blogs.sap.com/2020/08/17/cloud-integration-using-the-jdbc-adapter-to-implement-a-robust-scenario-that-handles-an-exception/)

</td>
</tr>
<tr>
<td valign="top">

Get file name when using the SFTP adapter

</td>
<td valign="top">

Use the header `CamelFileName` in the expression:`${header.CamelFileName}`.

More information:

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)

</td>
</tr>
<tr>
<td valign="top">

Get exception raised by the Camel framework

</td>
<td valign="top">

Use the following expression:

`${exception.message}`

</td>
</tr>
<tr>
<td valign="top">

Find out which operators are supported in routing conditions

</td>
<td valign="top">

More information: [Define Router](define-router-d7fddbd.md) 

</td>
</tr>
<tr>
<td valign="top">

Calculate hexadecimal values

</td>
<td valign="top">

Java example for calculating hex values:

`byte[] bytes = "testValue".getBytes(StandardCharsets.UTF_8);`

`String hexString = DatatypeConverter.printHexBinary(bytes);`

</td>
</tr>
<tr>
<td valign="top">

Get the Camel exchange ID \(for example, to uniquely relate a step or another property to a Camel exchange\)

</td>
<td valign="top">

Use the following expression:

`${exchangeId}`

</td>
</tr>
</table>

