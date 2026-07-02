<!-- loio6a6727ca4f9140b7891e1e8e01714c16 -->

# Artificial Intelligence

As a tenant administrator, you can activate and manage artificial intelligence features for your organization. These features allow users to simplify integrations, enhance workflow efficiency, and uncover actionable insights for better decision-making.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

You can activate the following features depending upon the capabilities you've activated in your SAP Integration Suite tenant. See [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md).

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

AI-assisted Error Resolution

</td>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

Use artificial intelligence to analyze and resolve message processing errors.

</td>
<td valign="top">

[AI-assisted Error Resolution](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/f27f95d7b90b4f13aea22b399418b702.html "Use artificial intelligence to analyze and resolve message processing errors efficiently.") :arrow_upper_right:

</td>
<td valign="top">

[PI\_Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?locale=en-US)

[PI\_Integration\_Developer](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?locale=en-US)

</td>
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

This feature is always activated to ensure optimized designing of integration flows and can't be deactivated. See [Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

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

-   [Generate Integrations with AI Assistance](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:
-   [Optimize Groovy Scripts with AI](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/3b7a5a1258ea469b963dc047c3f443a0.html "Enhance your Groovy scripts using Generative AI.") :arrow_upper_right: 



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

[Anomaly Detection](https://help.sap.com/viewer/6afa6d14ff6d4006b5614676722ef006/CLOUD/en-US/7a4fe7d85e10416e9dd63f98ccd780b2.html "Anomaly detection is an AI-based feature that involves the identification of patterns or data points that deviate significantly from normal behavior or expected patterns. This feature allows you to proactively identify and respond to unusual patterns or deviations in API traffic, thereby ensuring the security, reliability, and optimal performance of APIs.") :arrow_upper_right: 

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

[Predictions](https://help.sap.com/viewer/6afa6d14ff6d4006b5614676722ef006/CLOUD/en-US/823bcd7727944ba9b09b659988d394f2.html "In addition to anomaly detection, we have now introduced Predictions, an AI-based feature that can forecast future API call volumes based on past call data. With this new feature, you can identify trends in API traffic and view predictions for upcoming API call volumes. Predictions are available for all APIs that meet the minimum data requirement of at least 3 months of API call volume data. Additionally, it offers customizable options, allowing you to select specific APIs, choose the prediction duration, and set the frequency according to your preferences.") :arrow_upper_right: 

</td>
<td valign="top">

[APIPortal.Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/roles-collections-in-api-management-draft?version=CLOUD)

</td>
</tr>
<tr>
<td valign="top">

Generation of OpenAPI Specification

</td>
<td valign="top">

API Management

</td>
<td valign="top">

Upon activation, you can leverage AI assistance to automatically generate an OpenAPI Specification while creating an API artifact.

</td>
<td valign="top">

[Generate OpenAPI Specification with AI Assistance](https://help.sap.com/viewer/6afa6d14ff6d4006b5614676722ef006/CLOUD/en-US/5ec68dba721f414ca532fcc62f61706a.html "You can use AI assistance to automatically generate an OpenAPI specification while creating an API artifact. The AI analyzes your API design inputs and helps you quickly create a well-structured specification. This reduces manual effort and maintains consistency with OpenAPI standards.") :arrow_upper_right: 

</td>
<td valign="top">

[PI\_Administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?locale=en-US)

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

Upon deactivation of this service, MIG and MAG proposals will not be accessible to the tenant, and data won’t be collected from this tenant anymore \(although this will only impact future data collection, leaving previously collected data unaffected\).

</td>
<td valign="top">

[Settings for MIGs and MAGs](https://help.sap.com/viewer/986600e940714dee8ed03f126ee7efca/CLOUD/en-US/4c442af844e54848ad66f071ae8233ee.html "") :arrow_upper_right:

</td>
<td valign="top">

[iadv-content-administrator](https://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?locale=en-US)

</td>
</tr>
</table>

