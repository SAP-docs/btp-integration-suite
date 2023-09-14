<!-- loiofb24f52d522b4a3b84c762ff7e085861 -->

# Environment Variables

You can use environment variables in integration flows to address technical details such like, for example, the region where Cloud Integration is deployed.

> ### Note:  
> Example use case:
> 
> You can get the tenant name from an environment variable and use this information to specify a tenant-specific integration flow configuration. For example, you can specify different backend URLs for test and prod tenant, respectively.

There's a difference of these variables depending on whether you run Cloud Integration in the Neo or Cloud Foundry environment. Because of that, when you migrate from Neo to Cloud Foundry, you need to adapt all environment variables used in your integration content as a post-migration step.

The following table provides tha mapping of environment variables in Neo and Cloud Foundry.


<table>
<tr>
<th valign="top">

Variable Name \(Neo\)



</th>
<th valign="top">

Variable Name \(Cloud Foundry\)



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

HC\_APPLICATION

Example value: `abcd01iflmap`



</td>
<td valign="top">

TENANT\_NAME

Example value: `xyz001`



</td>
<td valign="top">

Sub domain of worker application \(associated with application identifier for worker node\)



</td>
</tr>
<tr>
<td valign="top">

HC\_APPLICATION\_URL

Example value: `abcd01iflmap.uvwxy.eu1.hana.ondemand.com`



</td>
<td valign="top">

TENANT\_NAME + IT\_SYSTEM\_ID + IT\_TENANT\_UX\_DOMAIN

Example value: `xyz001.it-cpi001.cfapps.eu10.hana.ondemand.com`



</td>
<td valign="top">

URL of the worker application sub domain



</td>
</tr>
<tr>
<td valign="top">

HC\_HOST

Example value: `hana.ondemand.com`



</td>
<td valign="top">

IT\_TENANT\_UX\_DOMAIN

Example value: `cfapps.eu10.hana.ondemand.com`



</td>
<td valign="top">

Base URL of the SAP BTP region host where the application is deployed



</td>
</tr>
<tr>
<td valign="top">

HC\_LOCAL\_HTTP\_PORT

Example value: `9001`



</td>
<td valign="top">

PORT

Example value: `8080`



</td>
<td valign="top">

HTTP port of the application bound to localhost



</td>
</tr>
<tr>
<td valign="top">

HC\_OP\_HTTP\_PROXY\_HOST



</td>
<td valign="top">

VCAP\_SERVICES



</td>
<td valign="top">

Host of the HTTP Proxy for on-premise connectivity



</td>
</tr>
<tr>
<td valign="top">

HC\_OP\_HTTP\_PROXY\_PORT

Example value: `20003`



</td>
<td valign="top">

VCAP\_SERVICES

Example value: `20003`



</td>
<td valign="top">

Port of the HTTP Proxy for on-premise connectivity



</td>
</tr>
<tr>
<td valign="top">

HC\_REGION

Example value: `EU_1`



</td>
<td valign="top">

IT\_TENANT\_UX\_DOMAIN

Example value: `cfapps.eu10.hana.ondemand.com`



</td>
<td valign="top">

Region where the application is deployed



</td>
</tr>
</table>

For more information, refer to:

-   [Using Cloud Environment Variables](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/d553d78bf9bd4ecbac201b873f557db6.html?q=environment%20variable) \(Neo\)

-   [Cloud Foundry Environment Variables](https://docs.cloudfoundry.org/devguide/deploy-apps/environment-variable.html)


