<!-- loio6a6727ca4f9140b7891e1e8e01714c16 -->

# Artificial Intelligence

As a tenant administrator, you can activate and manage artificial intelligence features for your organization. These features allow users to simplify integrations, enhance workflow efficiency, and uncover actionable insights for better decision-making.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

You can activate the following features depending upon the capabilities you've activated in your SAP Integration Suite tenant. See [Activating and Managing Capabilities](../activating-and-managing-capabilities-2ffb343.md).

**AI Features**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Capability

</th>
<th valign="top">

Description

</th>
<th valign="top">

More Information

</th>
<th valign="top">

Required Role Collection

</th>
</tr>
<tr>
<td valign="top">

Flow Step Recommendations

</td>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

AI recommends the next flow steps, while adding flowsteps in your integration flow to help simplify the design process.

</td>
<td valign="top">

This feature is always activated to ensure optimized designing of integration flows and can't be deactivated. See [Creating an Integration Flow](creating-an-integration-flow-da53d93.md)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Generation of Integrations

</td>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

Upon activation, you can create integration flows with assistance from Generative AI.

</td>
<td valign="top" rowspan="2">

You can activate these features together. See

-   [Generate Integrations with AI Assistance](creating-an-integration-flow-da53d93.md#loioda53d93cd8fb47ff9ea55b6b278cd85e__steps_sh3_tcl_jt)
-   [Optimize Groovy Scripts](optimize-groovy-scripts-3b7a5a1.md) 

> ### Remember:  
> Currently, the feature is available only on few BTP regions. If your SAP Integration Suite tenant is hosted on one of these regions, you can use the feature:
> 
> -   Amazon Web Services – Japan \(Tokyo\)
> 
> -   Amazon Web Services – Europe \(Frankfurt\)
> 
> -   Amazon Web Services – Australia \(Sydney\)
> 
> -   Amazon Web Services – U.S. East \(VA\)



</td>
<td valign="top">

[PI\_Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?locale=en-US)

</td>
</tr>
<tr>
<td valign="top">

Script Optimization

</td>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

Upon activation, enhance your Groovy scripts using Generative AI.

</td>
<td valign="top">

[PI\_Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?locale=en-US)

</td>
</tr>
<tr>
<td valign="top">

Anomaly Detection

</td>
<td valign="top">

API Management

</td>
<td valign="top">

Upon activation, performs system-level checks in the background to identify deviations in API call patterns from expected behaviour.

</td>
<td valign="top">

[Anomaly Detection](anomaly-detection-7a4fe7d.md) 

</td>
<td valign="top">

[APIPortal.Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/roles-collections-in-api-management-draft?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

API Traffic Prediction

</td>
<td valign="top">

API Management

</td>
<td valign="top">

Upon activation, identifies API traffic trends and provides predictions for upcoming call volumes.

</td>
<td valign="top">

[Predictions](predictions-823bcd7.md) 

</td>
<td valign="top">

[APIPortal.Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/roles-collections-in-api-management-draft?version=CLOUD)

</td>
</tr>
<tr>
<td valign="top">

MIG & MAG Proposals

</td>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

Benefit from message detail proposals for MIGs and mapping entity proposals for MAGs.

Upon deactivation of this service, MIG and MG proposals will not be accessible to the tenant, although this will only impact future data collection, leaving previously collected data unaffected.

</td>
<td valign="top">

[MIGs and MAGs](migs-and-mags-4c442af.md)

</td>
<td valign="top">

[iadv-content-administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?locale=en-US)

</td>
</tr>
</table>

