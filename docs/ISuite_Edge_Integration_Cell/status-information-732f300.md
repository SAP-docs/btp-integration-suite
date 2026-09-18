<!-- loio732f3005e69f4d309784ed7ad2e9ff2c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Status Information

Get status information on your Edge Integration Cell components.



<a name="loio732f3005e69f4d309784ed7ad2e9ff2c__overview"/>

## Overview

The *Status Information* card provides an overview of your Edge Integration Cell's health. The card summarizes the following key status indicators so that you can quickly identify whether attention is required.


<table>
<tr>
<th valign="top">

Item

</th>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Edge Integration Cell Version*

</td>
<td valign="top">

*OK* \(:black_square_button: \)

</td>
<td valign="top">

The Edge Integration Cell version is up-to-date and no upgrade is necessary.

> ### Note:  
> The *OK* status means there is no newer minor version. The status ignores the patch version.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Warning* \(<span class="SAP-icons-V5"></span> \)

</td>
<td valign="top">

A new version of the Edge Integration Cell is available. Upgrade to this version before certain actions are blocked. For more information, see [Upgrade Edge Integration Cell](upgrade-edge-integration-cell-27c3926.md).

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Error* \(<span class="SAP-icons-V5"></span>\)

</td>
<td valign="top">

Some of the actions are blocked. Upgrade to the latest Edge Integration Cell version. For more information, see [Upgrade Edge Integration Cell](upgrade-edge-integration-cell-27c3926.md).

</td>
</tr>
<tr>
<td valign="top">

*Default Virtual Host Status*

</td>
<td valign="top">

*OK* \( :black_square_button:\)

</td>
<td valign="top">

The default virtual host has been configured correctly.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Unavailable* \(<span class="SAP-icons-V5"></span> Unavailable \)

</td>
<td valign="top">

Since the default virtual host is not configured correctly, the Edge Integration Cell is not working properly. To solve the issue, assign the new runtime to either a new or an existing keystore. For more information, see [Deploy the Edge Integration Cell Solution](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/deploy-edge-integration-cell-solution?version=CLOUD).

</td>
</tr>
<tr>
<td valign="top">

*API Virtual Host Status*

</td>
<td valign="top">

*OK* \( :black_square_button:\)

</td>
<td valign="top">

The API virtual host has been configured correctly.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Not Configured*

</td>
<td valign="top">

The API virtual host has not been set up. To set it up, see [Modify Edge Integration Cell Solution Deployment Properties.](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/modify-edge-integration-cell-solution-deployment-properties?version=CLOUD&q=api+virtual+hoat)

> ### Note:  
> The API virtual host is optional. It is only required if you want to use Local OData API or if you have a setup with external Cloud Connector. .



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Unavailable* \(<span class="SAP-icons-V5"></span> \)

</td>
<td valign="top">

The API virtual host is configured, but the Gateway doesn't exist. To troubleshoot, follow the steps described in [Fix Connectivity Issues](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/fix-connectivity-issues?version=CLOUD) but with 'apiplan-gateway'.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*Unknown*

</td>
<td valign="top">

The version of Edge Integration Cell is too old and doesn't have the necessary API to retrieve the status. Please update the version.

</td>
</tr>
</table>

The card is clickable. Choose the card header or the *Connectivity* section to open the detailed view.



<a name="loio732f3005e69f4d309784ed7ad2e9ff2c__connectivity"/>

## Connectivity

The *Connectivity* tab displays the availability status of your virtual hosts and related configuration details.


<table>
<tr>
<th valign="top">

Item

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Default Virtual Host Status*

</td>
<td valign="top">

Indicates whether the default virtual host is available. *Available* means that it has been configured correctly. If it is *Unavailable*, the Edge Integration Cell is not working properly. To solve the issue, assign the new runtime to either a new or an existing keystore. For more information, see [Deploy the Edge Integration Cell Solution](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/deploy-edge-integration-cell-solution?version=CLOUD) .

</td>
</tr>
<tr>
<td valign="top">

*Default Virtual Host*

</td>
<td valign="top">

The host name of the default virtual host.

</td>
</tr>
<tr>
<td valign="top">

*External IP*

</td>
<td valign="top">

The external IP address of your Edge Integration Cell.

</td>
</tr>
<tr>
<td valign="top">

*API Virtual Host*

</td>
<td valign="top">

The name of the API virtual host of your Edge Integration Cell.

</td>
</tr>
<tr>
<td valign="top">

*API Virtual Host Status*

</td>
<td valign="top">

Indicates whether the API virtual host is configured. The following statuses are possible:

-   *Available* means that it has been configured correctly.
-   *Unavailable* means that the API virtual host is configured, but the Gateway doesn't exist. To troubleshoot, follow the steps described in [Fix Connectivity Issues](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/fix-connectivity-issues?version=CLOUD) but with 'apiplan-gateway'.
-   *Not Configured* means that it has not been set up. To set it up, see [Modify Edge Integration Cell Solution Deployment Properties.](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/modify-edge-integration-cell-solution-deployment-properties?version=CLOUD&q=api+virtual+hoat).

> ### Note:  
> The API Virtual Host is required for local OData API access.



</td>
</tr>
<tr>
<td valign="top">

*Operated By*

</td>
<td valign="top">

Indicates who operates this Edge Integration Cell; for example, *Customer*.

</td>
</tr>
</table>



<a name="loio732f3005e69f4d309784ed7ad2e9ff2c__communication-endpoints"/>

## Communication Endpoints

The *Communication Endpoints* tab lists the URLs of all SAP BTP cloud endpoints that are required for a functioning Edge Integration Cell.

> ### Remember:  
> Enable these endpoints in your firewall to ensure proper connectivity.

Each entry lists the *Service* and its corresponding *URL*. You can search for a specific service and copy any URL directly from the list.

For more information, see [Network and Communication Security for Edge Integration Cell](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/network-and-communication-security-for-edge-integration-cell?version=CLOUD).

