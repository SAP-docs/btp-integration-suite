<!-- loiobbfb41aa2c9b442cb7fb4396b9ae1401 -->

# Troubleshooting Transporting Content

Information on troubleshooting incidents and errors while transporting content.



<a name="loiobbfb41aa2c9b442cb7fb4396b9ae1401__section_rfn_52q_dfc"/>

## Issues with Transport Management Service \(TMS\)

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Failed to update the service instance

</td>
<td valign="top">

Failed Import from Transport Management Service to Cloud Integration

</td>
<td valign="top">

Perform the following steps:

1.  Delete the `process_integration_transport_instance` service in the SAP BTP subaccount of the target Cloud Integration tenant.
2.  Retrigger the export from the source Cloud Integration tenant.
3.  Retrigger the transport via TMS.



</td>
</tr>
</table>



<a name="loiobbfb41aa2c9b442cb7fb4396b9ae1401__section_jsb_xzx_dfc"/>

## Issues with Cloud Integration source tenant

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Desription

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

HTTP client error on Tenant settings page.

</td>
<td valign="top">

Unable to export MTAR file. Check the destination configuration - The **ContentAssemblyService** destination in source subaccount is not configured correctly.

</td>
<td valign="top">

Make sure that **ContentAssemblyService** destination is configured correctly and then retry transport.

For more information, see [Creating HTTP Destinations and Transport Route](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-http-destinations-and-transport-route-cloud-foundry?version=Cloud).

</td>
</tr>
<tr>
<td valign="top">

**Cloud Integration** destination is not found/not configured/not reachable/Validation failed

</td>
<td valign="top" rowspan="2">

Make sure that **Cloud Integration** destination is configured correctly and then retry transport.

Make sure that **TransportManagementService** destination is configured correctly and then retry transport.

For more information, see [3276989](https://me.sap.com/notes/3276989) - Check Configuration failed for Transport Management Service in Cloud Integration tenant settings.

</td>
</tr>
<tr>
<td valign="top">

**TransportManagementService** destination is not found/not configured

</td>
</tr>
</table>



<a name="loiobbfb41aa2c9b442cb7fb4396b9ae1401__section_dzh_kcy_dfc"/>

## Issues with Cloud Integration target tenant

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

com.sap.it.spc.ondemand.storage.exception.UniquenessViolationException

</td>
<td valign="top">

Uniqueness Violation Exception error occurred while importing MTAR content to SAP Cloud Integration tenant via CTS+/Cloud Transport Management

</td>
<td valign="top">

Perform he following steps:

1.  Open the package in the source tenant.
2.  Open the developer tools of the browser and open the *Network* tab.
3.  Select the *Artifacts* tab in the integration package.
4.  In the *Network* tab of the developer tools, look out for the network call `Artifacts?&$format=json`.
5.  Save its contents to a text-editing tool.
6.  Repeat the steps 1-5 in the target tenant.
7.  Compare the contents of both the tenants to identify the resource with same name or display name.



</td>
</tr>
<tr>
<td valign="top">

Transport package/artifact issue

</td>
<td valign="top">

The transport of a package or artifact from the source Neo tenant via CTS+ or Cloud Transport Management was successful, it is not showing up in the target tenant.

</td>
<td valign="top">

Ensure the destination in Solution Lifecycle Management of your target SAP BTP subaccount is set to the URL of the target Cloud Integration tenant.

For more information, see [Creating HTTP Destinations and Transport Route](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-http-destinations-and-transport-route?version=Cloud).

</td>
</tr>
</table>

