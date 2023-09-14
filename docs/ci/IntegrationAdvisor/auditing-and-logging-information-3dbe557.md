<!-- loio3dbe5576df864836b4ff54c42e7eef8f -->

# Auditing and Logging Information

Here you can find a list of the security events that are logged by Integration Advisor.

The audit log retrieval API allows you to retrieve the audit logs for your SAP Integration Advisor tenant in both Neo and Cloud Foundry environment.

The audit log retrieval follows the OData 4.0 standard, providing the audit log results as OData with collection of JSON entities.

> ### Note:  
> The examples contained in the table are taken from the usage of SAP Integration Advisor in the Cloud Foundry environment. Unless otherwise shown, the keywords used to identify an event are identical in both environments.

**Security Events Written in Audit Logs**


<table>
<tr>
<th valign="top">

Event grouping



</th>
<th valign="top">

What events are logged



</th>
<th valign="top">

How to identify related log events



</th>
<th valign="top">

Additional information



</th>
</tr>
<tr>
<td valign="top">

Message implementation guideline \(MIG\)



</td>
<td valign="top">

Delete MIG entity

Delete MIG version



</td>
<td valign="top">

-   Message Implementation Guideline

-   deleted successfully/deletion failed


Example:

When deleting a MIG successfully, the following event is written:

> ### Output Code:  
> ```
> Configuration modification message. Attribute with name "Message Implementation Guideline" and value "abcd1234" was deleted. 
> The attribute is a part of an object with type "Message Implementation Guideline" and id consisting of: message 
> "Message Implementation Guideline with objectGuid abcd1234 deleted successfully".
> ```



</td>
<td valign="top">

[Message Implementation Guidelines \(MIGs\)](message-implementation-guidelines-migs-f9f2bab.md) 



</td>
</tr>
<tr>
<td valign="top">

Mapping Guideline \(MAG\)



</td>
<td valign="top">

Delete MAG entity

Delete MIG version



</td>
<td valign="top">

-   Mapping Guideline

-   deleted successfully/deletion failed




</td>
<td valign="top">

[Mapping Guidelines \(MAGs\)](mapping-guidelines-mags-42124f4.md) 



</td>
</tr>
<tr>
<td valign="top">

Customer message



</td>
<td valign="top">

Delete customer message



</td>
<td valign="top">

-   Custom Message

-   deleted successfully/deletion failed




</td>
<td valign="top">

[Adding a Custom Message](adding-a-custom-message-8b7eb45.md) 



</td>
</tr>
<tr>
<td valign="top">

Value mapping



</td>
<td valign="top">

Delete global code value mapping



</td>
<td valign="top">

-   Code Value Mapping

-   deleted successfully/deletion failed




</td>
<td valign="top">

[Code Value Mapping](code-value-mapping-eb6dad8.md) 



</td>
</tr>
<tr>
<td valign="top">

Licenses



</td>
<td valign="top">

Create new license



</td>
<td valign="top">

-   Customer License

-   updated successfully/refresh failed for ...




</td>
<td valign="top">

[Managing Licence for Type Systems](managing-licence-for-type-systems-ed1e961.md) 



</td>
</tr>
<tr>
<td valign="top">

Licenses



</td>
<td valign="top">

Delete license



</td>
<td valign="top">

-   Customer License

-   deleted successfully/deletion failed




</td>
<td valign="top">

[Managing Licence for Type Systems](managing-licence-for-type-systems-ed1e961.md) 



</td>
</tr>
</table>

You can refer the following links to see the audit logging in Neo and Cloud Foundry environment :

-   [Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

-   [Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

