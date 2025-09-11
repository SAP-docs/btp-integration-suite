<!-- loioc744df5a043f49059e8c224240eb51e5 -->

# Policy Definition and Types of Policies

You can define the behavior of an API by using policies.

> ### Note:  
> This feature and the information is relevant only if you have activated Edge Integration Cell in your SAP Integration Suite tenant. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

A policy is a program that executes a specific function at runtime. They provide the flexibility to add common functionalities on an API without having to code them individually each time. Policies provide features to secure APIs, and control the API traffic.

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
<td valign="top" rowspan="4">

Security Policy

</td>
<td valign="top">

Authentication

</td>
<td valign="top">

API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and OAuth. For more information, see [Authentication](authentication-fa6eec4.md).

</td>
<td valign="top">

-   The position of the authentication policy on the flow is immutable and it’s the first policy on the flow.

-   Authentication policy is a mandatory policy and is added to request flow by default. Neither you can remove this policy, nor you can add another authentication policy to the flow.

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
<td valign="top">

API Validation

</td>
<td valign="top">

The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification. For more information, see [API Validation](api-validation-02ff41b.md).

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

 

</td>
</tr>
<tr>
<td valign="top">

Surge Protection

</td>
<td valign="top">

The surge protection policy protects the backend service against sudden traffic spikes. For more information, see [Surge Protection](surge-protection-3d14745.md).

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


[Create an API Artifact](create-an-api-artifact-c2fe62c.md "Create an API artifact to securely expose backend services, apply consistent governance by adding security and traffic management policies, and gain better visibility and control over how your APIs are accessed and used.")

[Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md "Add a resource to refer to individual endpoints or services.")

[Copy an API Artifact](copy-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API artifact but with some modifications or variations.")

[Deploy an API Artifact](deploy-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Externalize Parameter for API Artifact](externalize-parameter-for-api-artifact-ce0a468.md "You can use the externalization feature to define API policies and integration flows that can retrieve externalized configuration values during runtime. These parameters can be utilized later without modifying the standard API artifact.")

[Add Policies to the API Artifact](add-policies-to-the-api-artifact-c2b3e56.md "To enforce security or control API traffic, you can set rules on the API by adding policies and integration steps to the API artifact.")

