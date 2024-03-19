<!-- loioc744df5a043f49059e8c224240eb51e5 -->

# Policy Definition and Types of Policies Supported by Edge Integration Cell

You can define the behavior of an API by using policy steps.

> ### Note:  
> This feature and the information is relevant only if you have activated Edge Integration Cell in your SAP Integration Suite tenant. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

A policy is a program that executes a specific function at runtime. They provide the flexibility to add common functionalities on an API without having to code them individually each time. Policies provide features to secure APIs, and control the API traffic. You can also customize the behavior of an API by adding scripts and attaching them to policies.

****


<table>
<tr>
<th valign="top">

Policy Types

</th>
<th valign="top">

Policy

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Important Notes

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Security Policy

</td>
<td valign="top">

Authentication

</td>
<td valign="top">

Different API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth. For more information, see [Authentication](authentication-fa6eec4.md).

</td>
<td valign="top">

-   The position of the authentication policy step on the flow is immutable and it’s the first policy on the flow.

-   Authentication policy step is a mandatory policy step and is added to request flow by default. Neither you can remove this step, nor you can add another authentication policy step to the flow.

-   Authentication policy can be added to the request flow only once. All other policies can be added to the flow multiple times.




</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

This policy evaluates whether a user should be permitted to access a protected API. For more information, see [Authorization](authorization-6658409.md) 

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

JSON Threat Protection

</td>
<td valign="top">

Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings. For more information, see [JSON Threat Protection](json-threat-protection-c4991a6.md).

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Traffic Management Policies

</td>
<td valign="top">

Quota Policy

</td>
<td valign="top">

The Quota policy defines the number of request messages an application can submit to an API endpoint over a given period of time. For more information, see [Quota](quota-2aecf15.md).

</td>
<td valign="top">

When the quota limit specified in the policy is reached, the subsequent calls to the API proxy are rejected with the response code 429 \( request limit exceeded\). The rejection period lasts until the end of the quota window. Let's illustrate this with the following example:

The quota window opens at 00:00 \(12 AM\) and ends at 00:05 \(12:05 AM\). Let us assume that the quota allotted is 3 requests in the specified period of 5 minutes. At 00:03, if the quota limit is reached, the subsequent requests post 00:03 are rejected until the window is reset at 00:05.

</td>
</tr>
<tr>
<td valign="top">

Surge Protection

</td>
<td valign="top">

The surge protection policy protects the backend against sudden traffic spikes. For more information, see [Surge Protection](surge-protection-3d14745.md).

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

IP Filter

</td>
<td valign="top">

The IP filter policy allows or denies calls from specific IP addresses or address ranges. For more information, see [IP Filter](ip-filter-3a8b424.md) 

</td>
<td valign="top">

 

</td>
</tr>
</table>

**Related Information**  


[Add an API Artifact](add-an-api-artifact-c2fe62c.md "Add an API artifact to an package.")

[Adding Policy Steps to the API Artifact](adding-policy-steps-to-the-api-artifact-c2b3e56.md "To enforce security or control API traffic, you can set rules on the API by adding policy steps and integration steps to the API artifact.")

