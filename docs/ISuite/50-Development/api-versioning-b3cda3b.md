<!-- loiob3cda3bd21634a709b76bc6ae1b20c9b -->

# API Versioning

Versioning allows the creation and management of multiple releases of an API. You can version an API proxy when you want to improve, upgrade, or customize the functional behavior provided by a currently existing API proxy.



<a name="loiob3cda3bd21634a709b76bc6ae1b20c9b__section_btl_yfv_smb"/>

## Prerequisites

You need the APIPortal.Administrator role to use the versioning feature.



A new version of the API proxy is created when:

-   Incompatible changes, such as structural changes or changes in payload, are planned.
-   Additional policies are enforced, and a step-by-step client transition is needed.
-   API developer wants to model changes, which will be exposed as new version without affecting the consumption of existing API version .
-   There’s change in the billing model.

You can add a version to an API, when you’re creating the API proxy. This applies to creation from:

-   Integration Suite
-   Import of API definition file to the Integration Suite
-   Creation from API designer
-   Creation from APIs available from the SAP API Business Hub

Multiple versions of the API, can coexist at both runtime and design time.



The pattern for the name and base path for an API Proxy, when you’re using the version attribute, and have chosen, for example, v1 as the version is:


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

v1

</td>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Name\_v1

</td>
</tr>
<tr>
<td valign="top">

Base Path

</td>
<td valign="top">

/v1/SalesOrder

</td>
</tr>
</table>

In case you don’t provide name and base path in this required pattern, the system appends the version to the name, and prepends the version to the base path, to create a unique version of the API proxy.

For the version, we recommend that you use alphanumeric values. Based on the version you’ve provided, the system appends the version value to the API proxy name and base path, creating a unique version.

> ### Remember:  
> Once you've versioned an API Proxy, you can’t edit the version or the base path.

**Related Information**  


[Creating a Versioned API](creating-a-versioned-api-57abb00.md "Creating a versioned API Proxy from a deployed, versioned, or nonversioned API Proxy in the API Management, API Portal.")

[Create an API Proxy](create-an-api-proxy-c0842d5.md "This topic describes the steps to create an API proxy from the Integration Suite.")

[Create an API Proxy Using the API Designer](create-an-api-proxy-using-the-api-designer-26e1bbd.md "Model APIs in the Open API format that is available on the Integration Suite.")

[Copy an API Proxy](copy-an-api-proxy-23974d6.md "You can copy an API proxy in the same subscription.")

[Import an API Definition](import-an-api-definition-9342a93.md "This topic describes how to import an existing API definition into the Integration Suite.")

