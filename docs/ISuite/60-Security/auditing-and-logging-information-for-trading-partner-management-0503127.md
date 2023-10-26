<!-- loio0503127ec9b84d669d06c964fc42ca60 -->

# Auditing and Logging Information for Trading Partner Management 

Here you can find a list of the security events that are logged by Trading Partner Management.

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
</tr>
<tr>
<td valign="top">

Data Access

</td>
<td valign="top">

Access to contact person

</td>
<td valign="top">

action: Get Contact Person

</td>
</tr>
<tr>
<td valign="top">

Configuration Change

</td>
<td valign="top">

Tenant onboarding

</td>
<td valign="top">

action: AuditAction.aboutToCreate CFTenantOnboardingService.class

</td>
</tr>
<tr>
<td valign="top">

Configuration Change

</td>
<td valign="top">

Tenant offboarding

</td>
<td valign="top">

action: AuditAction.aboutToDelete CFTenantOnboardingService.class

</td>
</tr>
<tr>
<td valign="top">

Data Modification

</td>
<td valign="top">

Delete Artifact

</td>
<td valign="top">

action : AuditAction.aboutToDelete

objectType: Company, Certificate, TradingPartner, Coummunication Channel, Identifier,ResourceFile, Subsidary, SystemInstance, SystemType, TradingPartnerAgreement, TradingPartnerAgreementTemplate, TradingPartnerAttachment

</td>
</tr>
<tr>
<td valign="top">

Data Modification

</td>
<td valign="top">

Update Artifact

</td>
<td valign="top">

action : AuditAction.Update

objectType: Company, Certificate, TradingPartner, Coummunication Channel, Identifier,ResourceFile, Subsidary, SystemInstance, SystemType, TradingPartnerAgreement, TradingPartnerAgreementTemplate, TradingPartnerAttachment

</td>
</tr>
<tr>
<td valign="top">

Data Modification

</td>
<td valign="top">

Create Artifact

</td>
<td valign="top">

action : AuditAction.Create

objectType: Company, Certificate, TradingPartner, Coummunication Channel, Identifier,ResourceFile, Subsidary, SystemInstance, SystemType, TradingPartnerAgreement, TradingPartnerAgreementTemplate, TradingPartnerAttachment

</td>
</tr>
</table>

To know about the audit and loggging associated with Cloud Integration, see [Audit and Logging Information](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/d1c7bfe00b7c448ab56d7b4d454475f9.html).

