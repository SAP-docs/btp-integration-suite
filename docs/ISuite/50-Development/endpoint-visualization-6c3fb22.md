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

**SOAP Sender Adapter**:

For the SOAP sender adapter, you've 2 options to download the WSDL. You can download the WSDLwith or without policies. The WSDL with policies includes WS-policy assertions defining special requirements the sender system must adhere to. If the sender system doesn't understand WSDLs with policies, the WSDL without policies can be used instead.

**OData Sender Adapter**:

For integration flows with an OData sender adapter, you can download the EDMX files.

> ### Remember:  
> -   If such integration flows use "User Role" as authorization, download of EDMX files work only if you disable Single Sign-On \(SSO\) authentication in your browser.
> 
> -   For an OData API Project too, download of EDMX files work only if you disable Single Sign-On \(SSO\) authentication.

