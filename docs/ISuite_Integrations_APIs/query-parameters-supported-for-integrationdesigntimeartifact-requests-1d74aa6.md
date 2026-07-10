<!-- loio1d74aa60ebb4427e801c2912658333bc -->

# Query Parameters Supported for IntegrationDesigntimeArtifact Requests

IntegrationDesigntimeArtifacts request supports system query parameters for controlling the amount and order of data.

System Query Options are query string parameters that a client specifies to control the amount and order of the data that an OData API returns for the resource identified by the URI. The names of all System Query Options are prefixed with a "$" character.



<a name="loio1d74aa60ebb4427e801c2912658333bc__section_xs2_mwm_4fb"/>

## Reading DesigntimeArtifact


<table>
<tr>
<th valign="top">

Query

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

$select

</td>
<td valign="top">

You can select response properties based on the requirement.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')?$select=Id,Version`

</td>
</tr>
</table>



<a name="loio1d74aa60ebb4427e801c2912658333bc__section_kbv_dxm_4fb"/>

## Reading Resources


<table>
<tr>
<th valign="top">

Query

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

$select

</td>
<td valign="top">

You can select response properties based on the requirement.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$select=Name,ResourceType`

</td>
</tr>
<tr>
<td valign="top">

$count

</td>
<td valign="top">

Returns the total count of resources found in the artifact.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources/$count`

</td>
</tr>
<tr>
<td valign="top">

$orderby

</td>
<td valign="top">

Orders the collection of entries sorted either in ascending or descending order. By defaut the entries are sorted in ascending order. Use `desc` to sort all entries returned in descending oder.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$orderby=Name`or`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$orderby=Name,ResourceType desc`

</td>
</tr>
<tr>
<td valign="top">

$filter

</td>
<td valign="top">

Returns a subset of the entries, which matches the filter condition. The following filter conditions are supported:

-   Eq

-   ne


The following string functions are supported:

-   substringof

-   startswith

-   endswith




</td>
<td valign="top">

-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$filter=Name eq 'script1.groovy'`
-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$filter=Name ne 'script1.groovy'`
-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$filter=substringof('script1', Name) eq true`



</td>
</tr>
<tr>
<td valign="top">

$format

</td>
<td valign="top">

Response is received either in JSON or Atom XML format. The default format is **Atom XML**.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Resources?$format=json`

</td>
</tr>
</table>



<a name="loio1d74aa60ebb4427e801c2912658333bc__section_zzr_4bn_4fb"/>

## Reading Configurations


<table>
<tr>
<th valign="top">

Query

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

$select

</td>
<td valign="top">

You can select response properties based on the requirement.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$select=ParameterKey,ParameterValue`

</td>
</tr>
<tr>
<td valign="top">

$count

</td>
<td valign="top">

Returns the total count of resources found in the artifact.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations/$count`

</td>
</tr>
<tr>
<td valign="top">

$orderby

</td>
<td valign="top">

Orders the collection of entries sorted either in ascending or descending order. By defaut the entries are sorted in ascending order. Use `desc` to sort all entries returned in descending oder.

</td>
<td valign="top">

`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$orderby=ParameterKey`or`https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$orderby=ParameterKey,ParameterValue desc`

</td>
</tr>
<tr>
<td valign="top">

$filter

</td>
<td valign="top">

Returns a subset of the entries, which matches the filter condition. The following filter conditions are supported:

-   Eq

-   ne


The following string functions are supported:

-   substringof

-   startswith

-   endswith




</td>
<td valign="top">

-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$filter=ParameterKey eq '<key>'`
-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$filter=ParameterKey ne '<key>'`
-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$filter=substringof('<substring of key>', ParameterKey) eq true`



</td>
</tr>
<tr>
<td valign="top">

$format

</td>
<td valign="top">

Response is received either in JSON or Atom XML format. The default format is **Atom XML**.

</td>
<td valign="top">

-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$format=json`
-   `https://<tmnurl>/api/v1/IntegrationDesigntimeArtifacts(Id='<bundleid>',Version='<version>')/Configurations?$format=xml`



</td>
</tr>
</table>

