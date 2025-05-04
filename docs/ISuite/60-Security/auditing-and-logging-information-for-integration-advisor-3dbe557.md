<!-- loio3dbe5576df864836b4ff54c42e7eef8f -->

# Auditing and Logging Information for Integration Advisor

Here you can find a list of the security events that are logged by Integration Advisor.

The audit log retrieval follows the OData 4.0 standard, providing the audit log results as OData with collection of JSON entities.

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

[Message Implementation Guidelines \(MIGs\)](../50-Development/message-implementation-guidelines-migs-f9f2bab.md) 

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

[Mapping Guidelines \(MAGs\)](../50-Development/mapping-guidelines-mags-42124f4.md) 

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

[Adding a Custom Message](../50-Development/adding-a-custom-message-8b7eb45.md) 

</td>
</tr>
<tr>
<td valign="top">

Value mapping

</td>
<td valign="top">

Delete global code value mapping

Delete global code value mapping entity

Delete global code value mapping version

</td>
<td valign="top">

-   Code Value Mapping

-   deleted successfully/deletion failed




</td>
<td valign="top">

[Code Value Mapping](../50-Development/code-value-mapping-eb6dad8.md) 

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

[Managing Licence for Type Systems](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed1e961c636f4835aaa7248cf2488112.html "") :arrow_upper_right: 

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

[Managing Licence for Type Systems](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed1e961c636f4835aaa7248cf2488112.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Customer Codelist

</td>
<td valign="top">

Delete customer codelist entity

Delete customer codelist version

</td>
<td valign="top">

-   Customer Codelist
-   deleted successfully/deletion failed



</td>
<td valign="top">

[Deleting a Custom Codelist](../50-Development/deleting-a-custom-codelist-01ad9ee.md)

</td>
</tr>
</table>

To view the audit logging in Cloud Foundry environment, see [Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

