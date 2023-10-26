<!-- loioe5837f43d4b24177a04705e60e0423c8 -->

# Access Entity

API Management stores profile data for a range of entities, such as developers, applications, and API products. The access entity policy enables developers to retrieve those profiles during API proxy message processing. As such, the access entity policy functions as a policy-based runtime database lookup. The profile information returned by this policy can be used to enable dynamic behavior, such as conditional endpoint routing, flow execution, policy enforcement, and so on.

For example, you could use the access entity policy to get the profile for an application, and then extract a custom field \(such as a department name\) from the application profile. Using the department name as a variable, you could route the request to a specific backend service, or you could forward the department name to analytics to enable data accounting.

When a policy of type access entity is enforced:

1.  The policy sets an entity as an XML-formatted flow variable. The variable that is set is usually consumed by an extract variable or assign message policy.
2.  XPath is used to parse the desired properties from the profile.
3.  If the specified entity is not found, the policy returns ResourceNotFoundException.

Access entity can be used to access profiles for the following entities:

-   Application
-   API product
-   Consumer key
-   Developer
-   Company
-   Company developer

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!–- Use case 1 : Access developer from the current apikey which arrives in the request header
>  -->
> 
> <AccessEntity async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> 	<EntityType value="developer"/>
> 	<EntityIdentifier ref="request.header.apikey" type="consumerkey"/>
> </AccessEntity>
> 
> ```
> 
> > ### Note:  
> > For the above use case, if the policy is named as “AccessDeveloper” then a flow variable named “AccessEntity.AccessDeveloper” will hold the details of the developer in xml format. An extract variable policy can be used to extract any field from the developer details. Mentioned Below is an example to extract the developer e-mail into a flow variable named “developerEmail”.
> > 
> > > ### Sample Code:  
> > > ```
> > > <ExtractVariables async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> > > 	
> > > 	<Source>AccessEntity.AccessDeveloper</Source>
> > > 		<XMLPayload>
> > > 		<Variable name="developerEmail" type="string">
> > > 		<!-- Specifies the XPath defined for the variable -->
> > > 		<XPath>/Developer/Email</XPath>
> > > 	</Variable>
> > > 	</XMLPayload>
> > > </ExtractVariables>
> > > 
> > > ```
> 
> > ### Sample Code:  
> > ```
> > <!–- Use case 2 : Access product details from the current apikey which arrives in the request header
> > If the value for EntityType is changed to apiproduct, associated API product will be fetched populated in AccessEntity.{policy_name} flow variable. -->
> > 
> > <AccessEntity async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> > 	<EntityType value="apiproduct"/>
> > 	<EntityIdentifier ref="request.header.apikey" type="consumerkey"/>
> > </AccessEntity>
> > 
> > ```


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

EntityType \(Mandatory\)

</td>
<td valign="top">

The element indicates the type of entity to be retrieved from the data store. The permitted values for this element are provided in the table below.

Syntax: `<EntityType value="entity_type"/>`

</td>
</tr>
<tr>
<td valign="top">

EntityIdentifier \(Mandatory\)

</td>
<td valign="top">

The value that identifies the specific entity whose profile should be retrieved.

The `ref` attribute identifies the variable that provides the source of the identifier, for example, `request.queryparam.apikey`.

The `type` attribute identifies the EntityType populated by the referenced variable, such as `consumerkey`

Syxtax: `<EntityIdentifier ref="value_variable" type="identifier_type"/>`

> ### Sample Code:  
> Example
> 
> ```
> <?xml version="1.1" encoding="UTF-1" standalone="yes"?>
> <AccessEntity async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>     <DisplayName>FetchCompanyProfile</DisplayName>
>     <EntityType value="company"></EntityType>
>     <EntityIdentifier ref="request.queryparam.apikey" type="appid"/> 
> </AccessEntity>
> ```



</td>
</tr>
<tr>
<td valign="top">

SecondaryIdentifier \(Optional\)

</td>
<td valign="top">

This element is optional but if used, `ref` and `type` are mandatory.

Use this element when the EntityIdentifier does not return a unique value, for example, appname. You cannot use multiple SecondaryIdentifier elements.

The `ref` attribute identifies the variable that provides the source of the identifier, for example, request.queryparam.apikey.

The `type` identifies the entity type populated by the referenced variable, such as consumerkey. The use of multiple SecondaryIdentifier elements is not supported.

Syxtax: `<SecondaryIdentifier ref="value_variable" type="identifier_type"/>`

> ### Sample Code:  
> Example
> 
> ```
> <?xml version="1.1" encoding="UTF-1" standalone="yes"?><AccessEntity async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>     <DisplayName>FetchCompanyProfile</DisplayName>
>     <EntityType value="company"></EntityType>
>     <EntityIdentifier ref="developer.app.name" type="appname"/> 
>     <SecondaryIdentifier ref="developer.id" type="developerid"/> 
> </AccessEntity>
> ```



</td>
</tr>
</table>

The following table illustrates the values supported for `Entity Type` elements:


<table>
<tr>
<th valign="top">

EntityType Value

</th>
<th valign="top">

EntityIdentifier Types

</th>
<th valign="top">

SecondaryIdentifier Types

</th>
</tr>
<tr>
<td valign="top">

apiproduct

</td>
<td valign="top">

appid

</td>
<td valign="top">

apiresource

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

apiproductname

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

appname

</td>
<td valign="top">

apiresource

developeremail

developerid

companyname

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

consumerkey

</td>
<td valign="top">

apiresource

</td>
</tr>
<tr>
<td valign="top">

app

</td>
<td valign="top">

appid

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

appname

</td>
<td valign="top">

developeremail

developerid

companyname

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

consumerkey

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

authorizationcode

</td>
<td valign="top">

authorizationcode

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

company

</td>
<td valign="top">

appid

company

consumerkey

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

companydeveloper

</td>
<td valign="top">

companyname

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

consumerkey

</td>
<td valign="top">

consumerkey

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

consumerkey\_scope

</td>
<td valign="top">

consumerkey

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

developer

</td>
<td valign="top">

appid

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

consumerkey

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

developeremail

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

developerid

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

requesttoken

</td>
<td valign="top">

requesttoken

</td>
<td valign="top">

consumerkey

</td>
</tr>
<tr>
<td valign="top">

verifier

</td>
<td valign="top">

verifier

</td>
<td valign="top">



</td>
</tr>
</table>

**Related Information**  


[Assign Message](assign-message-523efe6.md "This policy allows you to create new or modify an existing HTTP request or response message.")

[Extract Variables](extract-variables-dad6ef6.md "The Extract variables policy can be used to extract content from the HTTP request or response messages of the API Proxy and assign that content to specific variables that can be accessed during the execution of the API Proxy.")

