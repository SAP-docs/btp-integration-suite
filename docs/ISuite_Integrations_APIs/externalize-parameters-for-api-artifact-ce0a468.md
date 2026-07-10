<!-- loioce0a468eeea043cab5477fa5702b3ce5 -->

# Externalize Parameters for API Artifact

You can use the externalization feature to define API policiesand integration flows that can retrieve externalized configuration values during runtime. These parameters can be utilized later without modifying the standard API artifact.

This feature allows for the declaration of parameters as variables, which can then be reused across multiple components within the same API artifact.

> ### Example:  
> When you add a policy to an API artifact, you have the option to externalize certain attributes of that policy for easier configuration across different environments or tenants. For example, let's say you added a Quota policy to an API and you wish to externalize the *Calls* attribute. You can define the attribute as **\{\{Calls\}\}** and set its default value to 5.
> 
> After saving and deploying the API artifact, you can download it and import it into another tenant. Once imported, the tenant will offer the ability to configure the *Calls* attribute directly without the need to modify the artifact via the *Configure* option on the UI. The value that you set in the configure view is the configured value. This means that you won't have to manually define all the attributes from scratch. Instead, you can focus on configuring only those attributes that have been externalized.
> 
> This approach simplifies the process and reduces the number of steps required to set up the API in different environments.

Remember that you can assign only one value to a parameter. But if you have a requirement to reuse a specific string in a value, then we recommended to split the value into multiple strings and define them to individual parameters as shown in the table.

The externalization parameters value field of an API artifact has been defined as following::


<table>
<tr>
<td valign="top">

Default Value

</td>
<td valign="top">

The parameter value defined by editing the standard artifact.

</td>
</tr>
<tr>
<td valign="top">

Configured Value

</td>
<td valign="top">

The parameter value set from the configure view.

> ### Note:  
> Configured values always override the default values.



</td>
</tr>
</table>

List of parameters that can be externalized for APIs and MCP servers on Integration Cell and Edge Integration Cell runtime:

**Externalized Parameters**


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Artifact

</th>
<th valign="top">

Parameters

</th>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

None

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

-   Authorization Type

    > ### Note:  
    > In Edge Integration Cell, Authorization Type is not supported.

-   Scope Key



</td>
</tr>
<tr>
<td valign="top">

IP Filter

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

-   Other Rules



</td>
</tr>
<tr>
<td valign="top">

Quota

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

-   Calls
-   Duration
-   Duration Unit



</td>
</tr>
<tr>
<td valign="top">

Surge Protection

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

-   Calls
-   Duration
-   Duration Unit



</td>
</tr>
<tr>
<td valign="top">

API Validation

</td>
<td valign="top">

-   API

-   MCP Server




</td>
<td valign="top">

None

</td>
</tr>
<tr>
<td valign="top">

JSON Threat Protection

</td>
<td valign="top">

-   API




</td>
<td valign="top">

-   Max Array Element Count
-   Max Depth
-   Max Object Count
-   Max Name Length
-   Max String Value Length
-   Max JSON Size \(KB\)



</td>
</tr>
<tr>
<td valign="top">

XML Threat Protection

</td>
<td valign="top">

-   API




</td>
<td valign="top">

-   Maximum Depth
-   Maximum Child Count per Element
-   Maximum Attribute per Element
-   Maximum Namespace per Element
-   Maximum XML Payload Size \(KB\)
-   Element Name Character Limit
-   Attribute Name Character Limit
-   Namespace Prefix Character Limit
-   Processing Instruction Target Character Limit
-   Text Character Limit
-   Attribute Value Character Limit
-   Namespace URL Character Limit
-   Processing Instruction Text Character Limit
-   Comment Character Limit



</td>
</tr>
</table>

