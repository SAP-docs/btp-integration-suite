<!-- loio4dfd54a7546c42cfb8dd157ab1355011 -->

# API Proxy Structure

During an import or export of an API proxy, the API proxy follows a specific predefined structure.

The structure of an API proxy is as follows:

**API Proxy Structure**


<table>
<tr>
<th valign="top">

Folder Name

</th>
<th valign="top">

Path

</th>
<th valign="top">

Contents

</th>
</tr>
<tr>
<td valign="top">

APIProxy

</td>
<td valign="top">

\\API Proxy

</td>
<td valign="top">

Root folder that contains the APIProxyEndPoint, APITargetEndPoint, APIResource, Documentation, FileResource, and Policy information.

</td>
</tr>
<tr>
<td valign="top">

APIProxyEndPoint

</td>
<td valign="top">

\\API Proxy\\APIProxyEndPoint

</td>
<td valign="top">

This folder has a `<Proxy Endpoint name>.xmlContains one file for every resource associated with the APIProxy. Each` file that contains information about Proxy Endpoint, resources, documentation, and the policy assignments on the proxy endpoint stream.

</td>
</tr>
<tr>
<td valign="top">

APIResource

</td>
<td valign="top">

\\API Proxy\\APIResource\\

</td>
<td valign="top">

`Contains one file for every resource associated with the APIProxy. Each<API Resource name>.xml`file contains the API resource details such as resource name, title, documentation, and so on.

</td>
</tr>
<tr>
<td valign="top">

Documentation

</td>
<td valign="top">

\\API Proxy\\Documentation

</td>
<td valign="top">

Contains one documentation file for every resource. Each document follows the naming convention `<APIResource name>_<language>.html`. For example, if the API Resource name is *PurchaseOrder* and the supported language is *English*, then the document file name is *PurchaseOrder\_en.html*. The file provides the documentation content relevant to the associated resource.

</td>
</tr>
<tr>
<td valign="top">

FileResource

</td>
<td valign="top">

\\API Proxy\\FileResource

</td>
<td valign="top">

Lists all the scripts attached to the policy. Only Java, Python, and XSL Scripts are supported. Follow the below naming convention:

-   Java Script: `<JavaScript name>.js`
-   Python script: `<PythonScript name>.py`
-   XSL script: `<XSLScript name>.xsl` 



</td>
</tr>
<tr>
<td valign="top">

Policy

</td>
<td valign="top">

\\API Proxy\\Policy

</td>
<td valign="top">

Contains a list of all policies attached to the API Proxy. Each policy is available as a separate file with the naming convention `<Policy name>.xml`. The folder should also contain a *defaultRaiseFaultPolicy.xml*.

</td>
</tr>
<tr>
<td valign="top">

`<APIProxyName>.xml` 

</td>
<td valign="top">

\\API Proxy\\`<APIProxyName>.xml` 

</td>
<td valign="top">

This file contains the header information of the proxy endpoint, target endpoint, policies, and file resources.

</td>
</tr>
</table>

> ### Note:  
> -   When you import an API proxy, ensure that the API proxy name in the `<APIProxy name>.xml` file and the value of the *base\_path* field \(inside the *APIProxyEndpoint* file\) is unique.
> -   If the API proxy does not contain any API resources, then the *APIResources*, *Documentation*, *FileResource*, and *Policy* folders are not required in the .zip file during import of API proxy.



## Route

A proxy endpoint can connect to one or more Target Endpoints. A route connects the proxy endpoint to the Target Endpoint. It determines which Target Endpoint to invoke based on the proxy endpoint configuration.

> ### Note:  
> You can also have an empty route, which means you do not define a Target Endpoint. You can define such routes when you do not want to forward the request message to any Target Endpoint. For example, flows that generate OAuth token.

**Route Rule**

All requests are forwarded to the respective Target Endpoints by implementing certain rules on the route. The Route Rule is basically a conditional statement that determines the Target Endpoint. When more than one Target Endpoint is available, the Route Rule evaluates the condition and, if true, the request is forwarded to the named target endpoint.

For more information on how to define multiple target endpoints using Route Rule, see [Enable Dynamic Routing](enable-dynamic-routing-49cbe91.md)



## Fault Rule

A lot of error conditions can arise when API proxies are servicing requests from applications. For example, you may encounter network issues when communicating with backend services, applications may present expired credentials, request messages may be incorrectly formatted, and so on. In such cases, it is important to handle these errors in a customized manner. When an API proxy encounters an error, the default behavior is to exit from the normal processing pipeline and to enter an error Flow. This error Flow bypasses any remaining processing Steps and Policies. As a result the raw error message or codes are returned to the requesting application. It is important to modify this behavior and improve usability. The API Platform enables you to customize exception handling by defining Fault Rules. Fault Rules can be attached to proxy endpoints, target endpoints, and Route rules. A Fault Rule is an XML configuration element that specifies:

-   A condition that classifies a fault based on the predefined category, subcategory, or name of the fault
-   One or more Policies that define the behavior of the FaultRule

