<!-- loio1425fe5aa47c4ceb81163d1f9dc7056f -->

# Value Mapping Example Requests

You can read, query, deploy, download, and upload a Value Mapping artifact using the OData API. You can also read and update the configurations of value mapping design time artifacts



<a name="loio1425fe5aa47c4ceb81163d1f9dc7056f__section_dpm_nmw_z4b"/>

## Filter All Value Mappings Based on Source and Target Value for Specific Bidirectional Agency Identifier

To filter all the value mappings based on the source and target value for a specific bidirectional agency identifier, send the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`/ValueMappingDesigntimeArtifacts(Id=<Id>,Version=<version>)/ValMapSchema(SrcAgency=<Agency_name>,SrcId=<source_Id,TgtAgency=<Agency_Name>,TgtId=<target_Id>)/ValMaps?$filter=Value/SrcValue eq <Source_Value> and Value/TgtValue eq <target_Value>` 

</td>
</tr>
</table>



<a name="loio1425fe5aa47c4ceb81163d1f9dc7056f__section_oyl_sh5_1pb"/>

## Create Value Mapping Using Function Import

To create a value mapping using function import *UpsertValMaps*, send the following call::


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

`/UpsertValMaps?Id=<Id>&Version=<version>&SrcAgency=<Agency_name>&SrcId=<source_Id>&TgtAgency=<Agency_Name>&TgtId=<target_Id>&SrcValue=<value>&TgtValue=<value>&IsConfigured=<true or false>` 

</td>
</tr>
</table>

> ### Note:  
> -   `IsConfigured` is used to change the state of the Bidirectional mapping. If the value is true, then the `ValMapSchema` is configured and if false it is meant for nonconfigured `ValMapSchema`.
> 
> -   Once a `ValMapSchema` is configured, it can't be changed. The value of `IsConfigured` should always be true for further operations as you cannot edit a configured content.



<a name="loio1425fe5aa47c4ceb81163d1f9dc7056f__section_f1v_ycj_vnb"/>

## Value Mapping Batch Requests

Batch operation with multiple queries and changesets:

> ### Sample Code:  
> ```
> 
> -batch
> Content-Type: multipart/mixed; boundary=changeset_77162fcd-b8da-41ac-a9f8-9357efbbd621
>  
> --changeset_77162fcd-b8da-41ac-a9f8-9357efbbd621
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> POST <operation> HTTP/1.1
>  
>  
> --changeset_77162fcd-b8da-41ac-a9f8-9357efbbd621
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> POST <operation> HTTP/1.1
>  
>  
> --changeset_77162fcd-b8da-41ac-a9f8-9357efbbd621--
>  
> --batch
> Content-Type: multipart/mixed; boundary=changeset_77162fcd-b8da-41ac-a9f8-9357efbbd622
>  
> --changeset_77162fcd-b8da-41ac-a9f8-9357efbbd622
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> POST <operation> HTTP/1.1
>  
>  
> --changeset_77162fcd-b8da-41ac-a9f8-9357efbbd622--
>  
> --batch
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> GET <operation> HTTP/1.1
>  
>  
> --batch
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> GET <operation> HTTP/1.1
>  
>  
> --batch
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> GET <operation> HTTP/1.1
>  
>  
> --batch--
> ```

