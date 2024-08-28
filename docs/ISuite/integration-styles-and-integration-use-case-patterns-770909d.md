<!-- loio770909d1a3d045bd96d3e8939208eabd -->

# Integration Styles and Integration Use Case Patterns

An integration style describes a basic category or type of integration, for example, process integration or the integration with things. Use case patterns help you to refine the integration styles relevant for your organization's integration strategy.

The following table shows some integration style examples and associated use case patterns.

****


<table>
<tr>
<th valign="top">

Integration Style

</th>
<th valign="top">

Use Case Patterns

</th>
</tr>
<tr>
<td valign="top">

Process integration

Integrate business processes that span multiple business applications.

</td>
<td valign="top">

A2A integration

B2B integration

Master data integration

</td>
</tr>
<tr>
<td valign="top">

Data integration

Synchronize data between business applications.

</td>
<td valign="top">

Data replication as required in extract, transform, and load \(ETL\) scenarios

Data virtualization

Data orchestration

</td>
</tr>
<tr>
<td valign="top">

Analytics integration

Derive and expose analytical data for business insights from business applications.

</td>
<td valign="top">

Embedded analytics

Cross-application analytics

</td>
</tr>
<tr>
<td valign="top">

User integration

Integrate user-centric applications with business applications.

</td>
<td valign="top">

UI integration

Mobile integration

Chatbot integration

</td>
</tr>
<tr>
<td valign="top">

Thing integration

Integrate real-world things with business applications.

</td>
<td valign="top">

Thing to analytics

Thing to process

Thing to data lake

</td>
</tr>
</table>

> ### Example:  
> If your integration architecture requires the integration of processes, the *process integration* integration style is relevant for you. If you need to consider the integration with sensors and other devices from the real world, the *thing integration* integration style is relevant for you.
> 
> If your integration strategy adheres to on the integration of processes, you can further refine the integration use case by specifying if you need to implement application-to-application \(A2A\) or business-to-business \(B2B\) scenarios. *A2A integration* and *B2B integration* are use case patterns related to the *process integration* integration style.

