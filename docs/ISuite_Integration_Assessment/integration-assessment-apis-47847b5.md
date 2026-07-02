<!-- loio47847b519d0849a4b9f91f60690d55b1 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Integration Assessment APIs

The following is the list of APIs used in Integration Assessment. For more information, see the [API Reference on SAP Business Accelerator Hub](https://hub.sap.com/package/SAPIntegrationAssessment/overview). You can also navigate to the API Reference from the Integration Assessment application. Select <span class="SAP-icons-V5"></span> User Actions from the top toolbar, then choose *API Reference*.



<a name="loio47847b519d0849a4b9f91f60690d55b1__section_uvw_dlf_t4b"/>

## Resources

****


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Domain

</td>
<td valign="top">

Domain is an area in a hybrid landscape where integration is needed.

Identifying integration domains provides the entry point into SAP Integration Solution Advisory Methodology.

See: [Integration Domains](integration-domains-e8360d2.md)

</td>
</tr>
<tr>
<td valign="top">

Style

</td>
<td valign="top">

Style is the basic integration category or type. Each integration style has specific characteristics and can be refined with use case patterns.

See: [Integration Styles and Integration Use Case Patterns](integration-styles-and-integration-use-case-patterns-770909d.md)

</td>
</tr>
<tr>
<td valign="top">

Use Case Pattern

</td>
<td valign="top">

Integration use-case patterns refine the integration styles identified for your organization's integration strategy.

</td>
</tr>
<tr>
<td valign="top">

Integration Pattern

</td>
<td valign="top">

To derive integration guidelines for complex landscapes, Integration patterns combine integration domains and integration styles to derive integration guidelines.

You can do an assessment of your integration architecture by adding the integration patterns that are relevant to your organization or that you might want to further evaluate.

</td>
</tr>
<tr>
<td valign="top">

Key Characteristic

</td>
<td valign="top">

Key Characteristic helps enterprise architects and integration architects to map integration styles to relevant capabilities of integration technologies.

</td>
</tr>
<tr>
<td valign="top">

Key Characteristic Group

</td>
<td valign="top">

Key characteristics group groups key characteristics and offers an additional layer for structuring for the key characteristics.

</td>
</tr>
<tr>
<td valign="top">

Key Characteristic Value

</td>
<td valign="top">

Values of key characteristics can be defined in order to express the variability a key characteristic can have.

In case of a key characteristic of type single, only one value for a key characteristic may exist.

</td>
</tr>
<tr>
<td valign="top">

Key Characteristic Recommendation

</td>
<td valign="top">

The available classification levels on how good a technology supports a specific key characteristic value of a key characteristic.

</td>
</tr>
<tr>
<td valign="top">

Deployment Model

</td>
<td valign="top">

Identifies how the software is hosted, for example, in the public cloud or on-premise.

</td>
</tr>
<tr>
<td valign="top">

Domain Determination

</td>
<td valign="top">

The available classification levels on how good a technology supports a specific key characteristic value of a key characteristic.

</td>
</tr>
<tr>
<td valign="top">

Application

</td>
<td valign="top">

Application is a software solution \(SaaS or on-premise\) used in the integration landscape. Integration assessment differentiates between application profile, which indicates the software group, and application instance, which is the actual runtime component.

The maximum number of applications is 20000.

</td>
</tr>
<tr>
<td valign="top">

Application Instance

</td>
<td valign="top">

Application instances are concrete instances of an application having a concrete deployment model.

The maximum number of application instances is 20000.

</td>
</tr>
<tr>
<td valign="top">

Technology

</td>
<td valign="top">

Middleware component that helps you solve your integration challenge. Integration technologies are the representative middleware components that are independent of the deployment model, namely on-premise or cloud. Integration Assessment differentiates between integration technology profile, which indicates the software group, and integration technology instance, which is the actual runtime instance.

The maximum number of technologies is 50.

</td>
</tr>
<tr>
<td valign="top">

Technology Instance

</td>
<td valign="top">

Technology instances are concrete instances of a technology having a concrete deployment model.

The maximum number of technology instances is 150.

</td>
</tr>
<tr>
<td valign="top">

Technology Domain

</td>
<td valign="top">

This is an association entity and describes the relation between a domain and a style.

</td>
</tr>
<tr>
<td valign="top">

Technology Style

</td>
<td valign="top">

This is an association entity and describes the relation between a technology and a style.

</td>
</tr>
<tr>
<td valign="top">

Technology Key Characteristic

</td>
<td valign="top">

This is an association entity and describes the relation between a key characteristic and a style.

</td>
</tr>
<tr>
<td valign="top">

Vendor

</td>
<td valign="top">

A vendor is a company that develops and sells software. You can choose an existing vendor or create a new vendor for an application or an integration technology.

The maximum number of vendors is 10000.

</td>
</tr>
<tr>
<td valign="top">

Request

</td>
<td valign="top">

A request is the entry point for a business solution request within the request workflow. One request can include multiple interface requests.

A business solution request can have different statuses. Some statuses are set automatically, while others can be updated by the user via UI or through API. Here are the supported actions and their corresponding statuses:

-   *Create*: The initial status of the request is `draft` \(set automatically\).
-   *Submit*: Changes the status to `new` \(updated by the user\).
-   *Assess Interface Requests*: The status shifts to `in progress` \(set automatically\).
-   *Complete*: Updates the status to `completed` \(updated by the user\).
-   *Reopen*: Switches the status back to `in progress` \(updated by the user\).



</td>
</tr>
<tr>
<td valign="top">

Request Line Item

</td>
<td valign="top">

A request line item is the entry point for an interface request within the request workflow. It links integration and message flows to the respective request.

</td>
</tr>
<tr>
<td valign="top">

Integration Flow

</td>
<td valign="top">

The set of one or more message flows that make up the intended integration scenario.

</td>
</tr>
<tr>
<td valign="top">

Message Flow

</td>
<td valign="top">

It represents a specific integration scenario between a source and target applications that are part of the integration flow.

</td>
</tr>
<tr>
<td valign="top">

Integration Flow Message Flow

</td>
<td valign="top">

This is an association entity and describes the relation between integration flows and message flows.

</td>
</tr>
<tr>
<td valign="top">

Request Line Item Technology Instance Decision

</td>
<td valign="top">

This entity describes the decision for a certain technology instance for a specific request line item.

</td>
</tr>
</table>

**Related Information**  


[Creating Service Instance and Service Key to enable API calling](creating-service-instance-and-service-key-to-enable-api-calling-749897f.md "")

[Integration Assessment API Reference on SAP Business Accelerator Hub](https://hub.sap.com/package/SAPIntegrationAssessment/overview)

