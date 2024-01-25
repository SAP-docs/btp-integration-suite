<!-- loio0a0bc81917e448518c1853f5d295102e -->

# Patch Archive 2021



<a name="loio0a0bc81917e448518c1853f5d295102e__section_u3g_xqj_hrb"/>

## October 2021

**Software Version: 1.135.\***


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.135.3

</td>
<td valign="top">

Error messages were popping up on the API Portal *Onboarding settings* page, and the page was not accessible. Backend configurations were applied to resolve this issue.

</td>
<td valign="top">

2021-10-20

</td>
</tr>
</table>



<a name="loio0a0bc81917e448518c1853f5d295102e__section_xhf_n44_sqb"/>

## September 2021

**Software Version: 1.134.\***


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.134

</td>
<td valign="top">

The following issues have been fixed with this patch:

-   While importing a certificate, the common name of the root certificate was displayed in the portal instead of the common name of the certificate. The data inconsistency encountered by the users while importing certificates has been resolved.
-   When multiple IDPs were configured, users couldn't approve the new developer registration requests in their Production environment, if the user ID of the developers weren’t their email IDs. With this patch, such restrictions on the User ID have been removed, and the users can approve the new developer registration requests in their Production environment.




</td>
<td valign="top">

2021-08-31

</td>
</tr>
</table>



<a name="loio0a0bc81917e448518c1853f5d295102e__section_gjf_4jx_gqb"/>

## August 2021

**Software Version: 1.133.\***


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.133.7

</td>
<td valign="top">

The deployment of an API Proxy would get timed out and fail when large number of Products were associated with it. This patch ensures that in such exceptional cases the deployment of the API Proxy wouldn't fail due to timeout.

</td>
<td valign="top">

2021-08-18

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.133.6

</td>
<td valign="top">

The following issues have been fixed with this patch:

-   Developer registrations in API Business Hub Enterprise would fail when multiple IDPs were associated with the API Management subaccount, and the user ID of the user being onboarded was alphanumeric and not an email ID.

-   The deployment of API Proxies would fail, if the API Proxies in the published Products had access control permissions defined.

-   API Proxy POST/PUT requests with gzip compressed content would fail.

-   Import of API Proxy would fail if it’s chained with another API Proxy. To resolve this issue, schema validation for the API Proxy chaining import flow has been enabled.




</td>
<td valign="top">

2021-08-13

</td>
</tr>
</table>

