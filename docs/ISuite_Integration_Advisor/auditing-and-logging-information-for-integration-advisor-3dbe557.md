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

-   Create MIG entity
-   Copy MIG entity
-   Create draft MIG version
-   Update MIG version
-   Activate MIG version
-   Delete MIG entity
-   Delete MIG version



</td>
<td valign="top">

Message implementation guideline

-   created successfully/creation failed
-   copied from source ... successfully/copy from source ... failed
-   draft created from source ... successfully/draft creation from source ... failed
-   updated successfully/update failed
-   activated successfully/activation failed
-   deleted successfully/deletion failed

Example:

When deleting a MIG successfully, the following event is written:

> ### Output Code:  
> ```
> Data modification message. Attribute with name "Message Implementation Guideline" and value "abcd1234" was deleted. 
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

-   Create MAG entity
-   Copy MAG entity
-   Create draft MAG version
-   Update MAG version
-   Activate MAG version
-   Delete MAG entity
-   Delete MAG version



</td>
<td valign="top">

Mapping guideline

-   created successfully/creation failed
-   copied from source ... successfully/copy from source ... failed
-   draft created from source ... successfully/draft creation from source ... failed
-   updated successfully/update failed
-   activated successfully/activation failed
-   deleted successfully/deletion failed



</td>
<td valign="top">

[Mapping Guidelines \(MAGs\)](mapping-guidelines-mags-42124f4.md) 

</td>
</tr>
<tr>
<td valign="top">

Pre-Transformation Script \(PTS\)

</td>
<td valign="top">

-   Create PTS entity
-   Update PTS entity
-   Delete PTS entity



</td>
<td valign="top">

Pre-transformation script

-   created successfully/creation failed
-   updated successfully/update failed
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

-   Create customer message
-   Update customer message
-   Delete customer message



</td>
<td valign="top">

Custom message

-   created successfully/creation failed
-   updated successfully/update failed
-   deleted successfully/deletion failed



</td>
<td valign="top">

[Adding a Custom Message](adding-a-custom-message-8b7eb45.md) 

</td>
</tr>
<tr>
<td valign="top">

Custom codelist

</td>
<td valign="top">

-   Create custom codelist
-   Create draft custom codelist
-   Update custom codelist
-   Activate custom codelist
-   Delete custom codelist entity or version



</td>
<td valign="top">

Custom codelist

-   created successfully/creation failed
-   draft created from source ... successfully/draft creation from source ... failed
-   updated successfully/update failed
-   activated successfully/activation failed
-   deleted successfully/deletion failed



</td>
<td valign="top">

[Code Value Mapping](code-value-mapping-eb6dad8.md)

[Deleting a Custom Codelist](deleting-a-custom-codelist-01ad9ee.md)

</td>
</tr>
<tr>
<td valign="top">

Value mapping

</td>
<td valign="top">

-   Create global code value mapping
-   Copy global code value mapping entity
-   Create draft global code value mapping version
-   Update global code value mapping version
-   Activate global code value mapping version
-   Delete global code value mapping entity
-   Delete global code value mapping version



</td>
<td valign="top">

Code value mapping

-   created successfully/creation failed
-   copied from source ... successfully/copy from source ... failed
-   draft created from source ... successfully/draft creation from source ... failed
-   updated successfully/update failed
-   activated successfully/activation failed
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

-   Create new license
-   Delete license
-   Refresh license list



</td>
<td valign="top">

Customer license

-   updated successfully/refresh failed
-   created successfully/creation failed
-   deleted successfully/deletion failed

License list

-   refreshed successfully/refresh failed



</td>
<td valign="top">

[Managing License for Type Systems](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed1e961c636f4835aaa7248cf2488112.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Artifact

</td>
<td valign="top">

-   Import artifacts
-   Export artifacts



</td>
<td valign="top">

Artifact

-   imported successfully/import failed
-   exported successfully/export failed



</td>
<td valign="top">

[Message Implementation Guidelines \(MIGs\)](message-implementation-guidelines-migs-f9f2bab.md)

[Mapping Guidelines \(MAGs\)](mapping-guidelines-mags-42124f4.md)

</td>
</tr>
<tr>
<td valign="top">

Authorization and Security

</td>
<td valign="top">

-   User authorization failure
-   License validation failure
-   Entity access validation failure
-   Trial license expiration
-   Unlock artifact \(admin only\)
-   Virus scan failure



</td>
<td valign="top">

Authorization

-   User authorization for resource ... failed

License

-   License validation for TypeSystem ... failed
-   Entity access validation for TypeSystem ... failed
-   Trial license expired for TypeSystem ...

Artifact

-   unlocked successfully/unlocked failed

Virus scan

-   Virus scan failed for resource ...



</td>
<td valign="top">

[Managing License for Type Systems](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed1e961c636f4835aaa7248cf2488112.html "") :arrow_upper_right:

</td>
</tr>
</table>

To view the audit logging in Cloud Foundry environment, see [Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

