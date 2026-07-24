<!-- loio165db68486ba44dda371f91e64381e5d -->

# Traffic Management Policies

Traffic management policies enable you to enforce quotas, protects the target backend against traffic spikes, and restrict access to your APIs based on specific IP addresses.



## Use

You use traffic management policies in an API artifact to:

-   Allow or deny API calls from specific IP addresses or address ranges to restrict access based on network origin.
-   Enforce quotas by defining the number of request messages an application can submit to an API endpoint over a given period of time.
-   Protect the backend service against sudden traffic spikes by controlling the rate of incoming requests.
-   Ensure API availability and stability by managing traffic flow and preventing backend overload.



## Traffic Management Policies


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

IP Filter

</td>
<td valign="top">

The *IP Filter* policy allows or denies calls from specific IP addresses or address ranges.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [IP Filter](ip-filter-3a8b424.md).

</td>
</tr>
<tr>
<td valign="top">

Quota

</td>
<td valign="top">

The *Quota* policy defines the number of request messages an application can submit to an API endpoint over a given period of time.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Quota](quota-2aecf15.md).

> ### Note:  
> If you intend to apply Quota policy to your API artifact for highly scalable workloads, it is recommended that you use Redis as the backing datastore when deploying the API artifact on Edge Integration Cell runtime to ensure optimal performance. For more information, see [Deploy the Edge Integration Cell Solution](https://help.sap.com/viewer/caeaa5e76f8c486ebea167938fa1f40b/CLOUD/en-US/ab81b845230742b4aa863fb27644d439.html "Get to know the steps needed to create the Edge Node as a Runtime Location in SAP Integration Suite.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

Surge Protection

</td>
<td valign="top">

The *Surge Protection* policy protects the backend service against sudden traffic spikes.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Surge Protection](surge-protection-3d14745.md).

> ### Note:  
> If you intend to apply Surge Protection policy to your API artifact for highly scalable workloads, it is recommended that you use Redis as the backing datastore when deploying the API artifact on Edge Integration Cell runtime to ensure optimal performance. For more information, see [Deploy the Edge Integration Cell Solution](https://help.sap.com/viewer/caeaa5e76f8c486ebea167938fa1f40b/CLOUD/en-US/ab81b845230742b4aa863fb27644d439.html "Get to know the steps needed to create the Edge Node as a Runtime Location in SAP Integration Suite.") :arrow_upper_right:.



</td>
</tr>
</table>

