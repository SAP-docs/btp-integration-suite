<!-- loiob996c4fbfc6e4aa2b01c0f8df32bfeef -->

# Integration Adapter Example Requests



<a name="loiob996c4fbfc6e4aa2b01c0f8df32bfeef__section_dpm_nmw_z4b"/>

## Deploy an Integration Adapter

To deploy an integration adapter, send the following call:


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

`/api/v1/DeployIntegrationAdapterDesigntimeArtifact?Id='SubsystemSymbolicName1'` 

</td>
</tr>
</table>

-   Import an integration adapter with the symbolic name *SubsystemSymbolicName1*.

-   Send the request as given in the following example.

    > ### Example:  
    > For deploying an integration adapter, the URL is given in the following format: `https://<host address>/api/v1/DeployIntegrationAdapterDesigntimeArtifact?Id='SubsystemSymbolicName1'`

    The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).




<a name="loiob996c4fbfc6e4aa2b01c0f8df32bfeef__section_jrm_fj5_1pb"/>

## Delete an Integration Adapter

To delete an integration adapter, send the following call:


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

DELETE

</td>
<td valign="top">

`/api/v1/IntegrationAdapterDesigntimeArtifacts(Id='SubsystemSymbolicName1')` 

</td>
</tr>
</table>

-   Import the integration adapter with the symbolic name *SubsystemSymbolicName1*.

-   Send the request as given in the following example.

    > ### Example:  
    > For deleting an integration adapter, the URL is given in the following format: `https://<tenant url>/api/v1/IntegrationAdapterDesigntimeArtifacts(Id='SubsystemSymbolicName1')`


