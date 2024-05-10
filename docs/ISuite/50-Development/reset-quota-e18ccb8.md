<!-- loioe18ccb8f3e284f02b423e320a1f48bc1 -->

# Reset Quota

The Reset Quota policy enables you to reset the limit for a specified Quota policy.

For example, you can use this policy to reset a Quota counter when additional API calls are to be made. Attach this policy before the Quota policy that you intend to reset.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy will reset the Quota policy by 100 calls when triggered, if the quota for a user is over when this policy is triggered this will allow user to make another 100 calls -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <ResetQuota async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Quota name="impose-quota">
>         <Identifier ref="request.queryparam.apiKey">
>             <Class ref="request.header.classIdentifier>
> 		  <Allow>100</Allow>
>         </Identifier>
>     </Quota>
> </ResetQuota>
> ```

**`<Quota>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Quota` \(Mandatory\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the name of the Quota policy whose counter should be reset.

> ### Sample Code:  
> ```
> <Quota name="quotaName"  ref="request.header.quotapolicy">
>    <Identifier name="identifierName" ref="request.header.identifier">
>       <Allow>100</Allow>
>    </Identifier>
> </Quota>
> ```



</td>
</tr>
</table>

**Attributes of the `<Quota>` element**

> ### Note:  
> Both `name` and `ref` are optional but at least one of the attributes should be used.


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`name`\(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the name of the target Quota policy.

</td>
</tr>
<tr>
<td valign="top">

`ref` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

A flow variable that contains the `name` of the target Quota policy. If both `ref` and `name` are specified, then `ref` gets priority. If `ref` does not resolve at runtime, then `name` is used.

</td>
</tr>
</table>

**`<Identifier>` element**

> ### Note:  
> Both `name` and `ref` are optional but at least one of the attributes should be used.


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Identifier` \(Mandatory\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

String

</td>
<td valign="top">

Specifies the name of the client.

> ### Sample Code:  
> ```
> <Quota name="quotaName"  ref="request.header.quotapolicy">
>    <Identifier name="identifierName" ref="request.header.identifier">
>       <Allow>100</Allow>
>    </Identifier>
> </Quota>
> ```



</td>
</tr>
</table>

**Attributes of the `<Identifier>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`name`\(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

String

</td>
<td valign="top">

Specifies the name of the count identifier in the target Quota policy.

</td>
</tr>
<tr>
<td valign="top">

`ref` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

A flow variable that contains the name of the count identifier in the target Quota policy. If both `ref` and `name` are specified, then `ref` gets priority. If `ref` does not resolve at runtime, then `name` is used.

</td>
</tr>
</table>

**`<Allow>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Allow` \(mandatory\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Specifies the message count to which the Quota will be reset.

> ### Sample Code:  
> ```
> <Quota name="quotaName"  ref="request.header.quotapolicy">
>    <Identifier name="identifierName" ref="request.header.identifier">
>       <Allow>100</Allow>
>    </Identifier>
> </Quota>
> ```



</td>
</tr>
</table>

**`<Class>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Class`\(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the class for which the Quota counter is updated.

> ### Sample Code:  
> ```
> <Identifier name="_default">
>    <Class ref="request.header.classIdentifier">
>      <Allow>100</Allow>
>    </Class>
> </Identifier>
> ```



</td>
</tr>
</table>

**`ref` attribute of the `<Allow>` and <Class\> elements**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`ref` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

A flow variable that contains the name of the count identifier in the target Quota policy.

</td>
</tr>
</table>

Reset Quota policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error code

</th>
<th valign="top">

Message

</th>
</tr>
<tr>
<td valign="top">

InvalidRLPolicyDefinition

</td>
<td valign="top">

Invalid rate limit policy \{0\}

</td>
</tr>
<tr>
<td valign="top">

NoRLPolicy

</td>
<td valign="top">

Quota policy \{0\} is not attached.

</td>
</tr>
<tr>
<td valign="top">

InvalidCount

</td>
<td valign="top">

Invalid count value \{0\} for identifier \{1\} in \{2\}

</td>
</tr>
<tr>
<td valign="top">

FailedToResolveAllowCountRef

</td>
<td valign="top">

Failed to resolve allow count reference \{0\} for identifier \{1\} in \{2\}

</td>
</tr>
</table>

**Related Information**  


[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

