<!-- loioc90a80c97e094406bdd2e6ce3dfc151e -->

# Metadata

Due to the OData protocol being self-documented, developers can ensure that their application is compatible with the specific business data graphs that they are accessing.

This is possible by programmatically reviewing the detailed metadata available to them at runtime as follows:


<table>
<tr>
<th valign="top">

Metadata API

</th>
<th valign="top">

URL to Use

</th>
</tr>
<tr>
<td valign="top">

The list of business data graphs in the landscape

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/api`

Example: `https:// is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api`

</td>
</tr>
<tr>
<td valign="top">

The list of all services \(namespaces\)

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>`

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1`

</td>
</tr>
<tr>
<td valign="top">

The list of entities in a specific business data graph

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>`

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.s4` 

</td>
</tr>
<tr>
<td valign="top">

The OData EDMX metadata of a service \(namespace\)

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/$metadata`

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.s4/$metadata`

</td>
</tr>
</table>


<table>
<tr>
<th valign="top">

Catalog API

</th>
<th valign="top">

URL to use

</th>
</tr>
<tr>
<td valign="top">

The list of business data graphs in the landscape

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/catalog`

``

Example:`https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/catalog`

</td>
</tr>
<tr>
<td valign="top">

The list of all services \(namespaces\)

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/catalog/<bdg>`

``

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/catalog/v1`

</td>
</tr>
<tr>
<td valign="top">

The list of entities in a specific business data graph

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/catalog/<bdg>/<namespace>`

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/catalog/v1/sap.s4`

</td>
</tr>
<tr>
<td valign="top">

The OpenAPI metadata of one entity

</td>
<td valign="top">

`https://<subdomain>.a.integration.cloud.sap/graph/catalog/<bdg>/<namespace>/<entity>`

Example: `https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/catalog/v1/sap.s4/A_BusinessPartner`

</td>
</tr>
</table>

