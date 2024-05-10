<!-- loio6c3fb226fe91412d94bbb63ac834b35a -->

# Endpoint Visualization

You can visualize the adapter endpoints in the *Manage Integration Content* section.

With the new release of integration service, the endpoint definitions of some adapters are extracted.

Go to *Manage Integration Content* and select an integration flow from the list and go to *Endpoints* in the detailed view.

You can visualize the endpoint URL and the definition as specified in the following table, copy the URL to the clipboard or download the definition:


<table>
<tr>
<th valign="top">

Adapter

</th>
<th valign="top">

Show Endpoint \(access\) URL

</th>
<th valign="top">

Show Definition

</th>
</tr>
<tr>
<td valign="top">

SOAP

</td>
<td valign="top">

**X** 

</td>
<td valign="top">

**X** 

</td>
</tr>
<tr>
<td valign="top">

IDOC

</td>
<td valign="top">

**X** 

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

HTTP

</td>
<td valign="top">

**X** 

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

AS2

</td>
<td valign="top">

**X** 

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

XI Adapter

</td>
<td valign="top">

**X**

</td>
<td valign="top">

 

</td>
</tr>
</table>



<a name="loio6c3fb226fe91412d94bbb63ac834b35a__section_pyh_p4m_hyb"/>

## Download Options

Depending on the sender adapter type contained in the integration flow, you have different download options.


<table>
<tr>
<th valign="top">

Adapter

</th>
<th valign="top">

Download Options

</th>
</tr>
<tr>
<td valign="top">

SOAP sender adapter

</td>
<td valign="top">

-   *Download*

    > ### Caution:  
    > In case you want to download the WSDL in Cloud Foundry via a technical client, you need a service instance of the plan `api` assigned with the`MonitoringDataRead` role. It is not possible to use a service instance of plan `integration flow`.
    > 
    > See: [Creating Service Instance and Service Key for Inbound Authentication](../40-RemoteSystems/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md) and [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

-   *WSDL Policies*

    There are two options to download the WSDL: with or without policies. The WSDL with policies includes WS-policy assertions defining special requirements the sender system must adhere to. If the sender system doesn't understand WSDLs with policies, the WSDL without policies can be used instead.




</td>
</tr>
<tr>
<td valign="top">

OData sender adapter

</td>
<td valign="top">

*Download*

You can download the EDMX files.

> ### Remember:  
> -   If such integration flows use *User Role* as authorization, download of EDMX files work only if you disable Single Sign-On \(SSO\) authentication in your browser.
> 
> -   For an OData API Project, download of EDMX files work only if you disable Single Sign-On \(SSO\) authentication.



</td>
</tr>
</table>

