<!-- loio19c06541b12140579a09dbe536fb2320 -->

# Key Components of an API

This section introduces you to some of the key components of an API that you need to know before building APIs.




<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Proxy

</td>
<td valign="top">

Is a discrete representation of an API entity that abstracts the actual proxy end point properties at one end and the actual target endpoint \(the endpoint that is relevant for the end user to invoke\) at the other end. It also includes other properties that describe the policies that need to be invoked on the API, the attachments, and documents, and other artifacts that are relevant to the API.

</td>
</tr>
<tr>
<td valign="top">

Proxy Endpoint

</td>
<td valign="top">

Manages interactions with API consumers. Consumers of the API normally interact with the base path of the API and are attached to policy entities that operate to define quota, access limiters, and so on.

</td>
</tr>
<tr>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

Manages interactions with the backend service endpoint on behalf of consumer applications. Backend endpoint forwards request messages to the proper backend service.

</td>
</tr>
<tr>
<td valign="top">

API Resource

</td>
<td valign="top">

Individual business entities that an API proxy contains. For example: BusinessPartnerCollection is an API resource that the API administrator would like to present via an API Proxy entity.

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Is the object representation to specify if GET, POST, PUT, and DELETE calls are specified.

</td>
</tr>
<tr>
<td valign="top">

Policy

</td>
<td valign="top">

The runtime engine of SAP Integration Suite is policy driven. This means that policies are decoupled from the service definition. They can be dynamically linked to these APIs or services to enforce minimal or maximum levels of operation and Quality of Service.

</td>
</tr>
<tr>
<td valign="top">

API Documentation

</td>
<td valign="top">

Describes each API resource in a simple and concise manner.

</td>
</tr>
</table>

**Related Information**  


[Different Methods of Creating an API Proxy](different-methods-of-creating-an-api-proxy-4ac0431.md "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.")

[Edit an API Proxy](edit-an-api-proxy-a64b952.md "Once you’ve created an API proxy you can further change the proxy, either on the Integration Suite, or by using the embedded API designer.")

[Additional Configurations](additional-configurations-de7285c.md " ")

