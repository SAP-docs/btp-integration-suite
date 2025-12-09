<!-- loioce0a468eeea043cab5477fa5702b3ce5 -->

# Externalize Parameter for API Artifact

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

**Related Information**  


[Create an API Artifact](create-an-api-artifact-c2fe62c.md "Create an API artifact to securely expose backend services, apply consistent governance by adding security and traffic management policies, and gain better visibility and control over how your APIs are accessed and used.")

[Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md "Add a resource to refer to individual endpoints or services.")

[Copy an API Artifact](copy-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API artifact but with some modifications or variations.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policies.")

[Deploy an API Artifact](deploy-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Design Guidelines for API Artifact](design-guidelines-for-api-artifact-7e704f7.md "A set of best practices to ensure that APIs are designed for consistency, scalability, security, and ease of maintenance within SAP Integration Suite.")

