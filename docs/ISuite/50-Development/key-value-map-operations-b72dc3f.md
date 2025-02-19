<!-- loiob72dc3f262c1441587e76d0e808a12fe -->

# Key Value Map Operations

The key value map operations policy allows you to create a key value map and perform update, read, and delete operations on the map.

Key Value Map Operations are typically used to store or retrieve long-lived information that needs to be reused over multiple request or response transactions.

> ### Note:  
> The policy doesn't currently support creating encrypted key value maps. You can use the UI or API for this purpose. However, you can update encrypted key value maps with the policy.

Key value refers to any arbitrary data in the format key=value, for example localhost=127.0.0.1,zip\_code=94110, or first\_name=Philip.

In the first example, localhost is a key, and 127.0.0.1 is a value.

Each key/value pair is stored in a map as an entry. A key/value map can store many entries. For example, say you need to store a list of IP addresses associated with various backend environments.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
>  <KeyValueMapOperations async="true" continueOnError="false" 
>      enabled="true" mapIdentifier="urlMapper" xmlns="http://www.sap.com/apimgmt">
>     <InitialEntries>
>        <Entry>
>           <Key>
>              <Parameter>key1</Parameter>
>           </Key>
>           <Value>val1</Value>
>        </Entry>
>        <Entry>
>           <Key>
>              <Parameter>var_name</Parameter>
>           </Key>
>           <Value>val1</Value>
>           <Value>val2</Value>
>        </Entry>
>     </InitialEntries>
>     <Put override="false">
>        <Key>
>           <Parameter>key1</Parameter>
>        </Key>
>        <Value ref="var_name"/>
>     </Put>
>     <Get assignTo="sapapim.empnumber" index="1">
>        <Key>
>           <Parameter ref="sapapim.empEmail"/>
>        </Key>
>     </Get>
>     <Delete>
>        <Key>
>           <Parameter>key1</Parameter>
>        </Key>
>     </Delete>
> 	<Scope>apiproxy</Scope>
>  </KeyValueMapOperations>
> 
> ```

**<mapIdentifier\> element**


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

`mapIdentifier` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies an identifier to be used when accessing a map created by this policy.

If you exclude this attribute, a KVM named `kvmap` is used.

</td>
</tr>
</table>

**<Scope\> element**


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

`Scope` \(Optional\)

</td>
<td valign="top">

environment

</td>
<td valign="top">

String

</td>
<td valign="top">

Defines the boundary of accessibility for key value maps..

The default value is environment. That is, by default, maps entries are shared by all API proxies running in an environment.

The valid values are apiproxy, environment, organization and policy.

If you set the scope to apiproxy, then the entries in the key value map are accessible only by the API Proxy that writes the values to the map.

> ### Note:  
> when accessing a map or map entry, you must specify the same scope value you used when the map was created. For example, if the map was created with a scope of apiproxy, you must use the apiproxy scope when retrieving its values, updating changes, or deleting entries.



</td>
</tr>
</table>

**<Entry\> element**


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

`Entry` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Seed values for key value maps, which are populated in the key value map when it’s initialized.

> ### Sample Code:  
> ```
> <InitialEntries>
>    <Entry>
>       <Key>
>          <Parameter>key1</Parameter>
>       </Key>
>       <Value>val1</Value>
>    </Entry>
>    <Entry>
>       <Key>
>          <Parameter>key1_variable</Parameter>
>       </Key>
>       <Value>val2</Value>
>       <Value>val3</Value>
>    </Entry>
> </InitialEntries>
> 
> ```



</td>
</tr>
</table>

**<InitialEntries\> element**


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

`InitialEntries` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Seed values for key value maps, which are populated in the key value map when it’s initialized. Make sure to specify the name of the key value map with the mapIdentifier attribute on the parent element.

When using this element, when you save the policy on a deployed version of the proxy, or deploy the API proxy bundle containing the policy with this element, the key\(s\) are automatically created in the key value map \(as unencrypted\). If the values in the policy are different than the values in the key value map, the values in the key value map are overwritten when the proxy is deployed. Any new keys/values are added to the existing key value map alongside the existing keys/values.

> ### Sample Code:  
> ```
> <InitialEntries>
>    <Entry>
>       <Key>
>          <Parameter>key1</Parameter>
>       </Key>
>       <Value>val1</Value>
>    </Entry>
>    <Entry>
>       <Key>
>          <Parameter>key2_variable</Parameter>
>       </Key>
>       <Value>val2</Value>
>       <Value>val3</Value>
>    </Entry>
> </InitialEntries>
> 
> ```

> ### Note:  
> Keys and values populated by this element must be literals.
> 
> > ### Sample Code:  
> > ```
> > <Parameter ref="request.queryparam.key">
> > ```
> 
> The example shown above isn't supported within this element.



</td>
</tr>
</table>

**<key\> element**


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

`key` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the key in a key/value map entry. A key can be composite, which means that more than one parameter can be appended to create the key. For example, userID and role might be combined to create a key.

> ### Sample Code:  
> ```
> <Key>
>      <Parameter>key1</Parameter>
>  </Key>
> 
> ```

See the <parameter\> element for information about how to set the key name.

</td>
</tr>
</table>

**<parameter\> element**


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

`parameter` \(Required\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

String

</td>
<td valign="top">

Specifies the key in a key/value pair. This element specifies the name when creating, putting, retrieving, or deleting the key/value pair.

-   A literal string

    > ### Sample Code:  
    > ```
    > <Key>
    >    <Parameter>stringliteral</Parameter>
    >  </Key>
    > 
    > ```

-   A variable to be retrieved at runtime

    > ### Sample Code:  
    > ```
    > <Key>
    >    <Parameter ref="var_name"/>
    >  </Key>
    > 
    > ```

-   A combination of variable references and literal strings

    > ### Sample Code:  
    > ```
    > <Parameter>targetendpoint</Parameter>
    >    <Parameter ref="api_proxy.name"/>
    >    <Parameter>size</Parameter>
    >  </Key>
    > 
    > ```


When the key element includes multiple Parameter elements, the effective key string is the concatenation of the values of each parameter, joined with a double underscore. For example, in the above example, if the api\_proxy.name variable has the value "def23", then the effective key will be targetendpoint\_\_def23\_\_size.

> ### Note:  
> Whether you're retrieving, updating, or deleting a key/value entry, the key name must match the name of the key in the key value map.



</td>
</tr>
</table>

**ref attribute of the <parameter\> element**


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

`ref`

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the name of a variable whose value contains the exact name of the key you want to create, retrieve, or delete.

</td>
</tr>
</table>

**<value\> element**


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

`value` \(Required\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

String

</td>
<td valign="top">

Specifies the value of a key.

You can specify the value as either a literal string or, using the ref attribute, as a variable to be retrieved at runtime.

> ### Sample Code:  
> ```
> <!-- Specify a literal value -->
> <Value>literalstring<Value>
> 
> ```

> ### Sample Code:  
> ```
> <!-- Specify the name of variable value to be populated at run time. -->
> <Value ref="var_name"/>
> 
> ```

You can include multiple <value\> elements to specify a multi-part value. Values are combined at run time.

In the following example, two keys ‘key1’ with values ‘val1’ and ‘val2’ and ‘key2’ with values ‘val3’ and ‘val4’ are added to the KVM:

> ### Sample Code:  
> ```
> <InitialEntries>         
>     <Entry>             
>        <Key>
>           <Parameter>key1</Parameter>
>        </Key>
>        <Value>val1</Value>
>        <Value>val2</Value>     
>     </Entry>
>     <Entry>
>        <Key>
>           <Parameter>key2</Parameter>
>        </Key>
>        <Value>val3</Value>
>        <Value>val4</Value>
>     </Entry>
>  </InitialEntries>
> 
> ```



</td>
</tr>
</table>

**ref attribute of the <value\> element**


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

`ref`

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the name of a variable whose value contains the key value\(s\) you want to set.

</td>
</tr>
</table>

**<Get\> element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Description

</th>
<th valign="top">

Attributes

</th>
<th valign="top">

 

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

`Get` \(Required if <Put\> or <Delete\> are not present\)

</td>
<td valign="top" rowspan="2">

Retrieves the value for the key specified.

At least one of <Get\>, <Put\>, or <Delete\> must be used.

Make sure to specify the name of the KVM with the mapIdentifier attribute on the parent element.

> ### Sample Code:  
> ```
> <Get assignTo="var5" index="1">         
>     <Key>             
>        <Parameter>key1</Parameter>         
>     </Key>     
>  </Get>
> 
> ```



</td>
<td valign="top">

`assignTo`

</td>
<td valign="top">

The variable to which the retrieved value must be assigned.

</td>
</tr>
<tr>
<td valign="top">

index

</td>
<td valign="top">

You can specify an index for a multivalued key. For example, if index=1, the value at index 1 is fetched and assigned to the variable. If not specified, all the values of that entry are assigned to the variable as java.util.List.

</td>
</tr>
</table>

**<Put\> element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Description

</th>
<th valign="top">

Attributes

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Put` \(Required if <Get\> or <Delete\> are not present\)

</td>
<td valign="top">

Writes a key/value pair to a key value map.

> ### Sample Code:  
> ```
> <Put override="false">         
>    <Key>             
>       <Parameter ref="mykeyvariable"/>         
>    </Key>         
>    <Value ref="myvalvariable1"/>     
> </Put>
> 
> ```



</td>
<td valign="top">

`override`

</td>
<td valign="top">

The default value is false.

If true, it overrides the value of a key.

</td>
</tr>
</table>

**<Delete\> element**


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

`Delete` \(Required if <Get\> or <Put\> are not present\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Deletes the specified key/value pair. At least one of <Get\>, <Put\>, or <Delete\> must be used.

Make sure to specify the name of the key value map with the ‘mapIdentifier’ attribute on the parent element.

> ### Sample Code:  
> ```
> <Delete>
>     <Key>
>        <Parameter>key1</Parameter>
>     </Key>
>  </Delete>
> 
> ```



</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Cause**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

SetVariableFailed

</td>
<td valign="top">

This error occurs when you attempt to fetch a value from an encrypted key-value map and assign it to a variable that doesn't have the "private" prefix in its name. This prefix is necessary for basic security measures during debugging, as it prevents the encrypted values from being displayed in API proxy Trace and debug sessions. For example:

> ### Sample Code:  
> ```
> <Get assignTo="private.encryptedVar" index="1">
>     <Key>
>       <Parameter>foo</Parameter>
>     </Key>
> </Get>
> ```



</td>
</tr>
<tr>
<td valign="top">

RemoveVariableFailed

</td>
<td valign="top">

Failed to remove variable \{0\} in KeyValueMapStepDefinition \{1\}

</td>
</tr>
<tr>
<td valign="top">

InvalidIndex

</td>
<td valign="top">

Invalid index \{0\} in KeyValueMapStepDefinition \{1\}

</td>
</tr>
<tr>
<td valign="top">

KeyIsMissing

</td>
<td valign="top">

Key element is missing in KeyValueMapStepDefinition \{0\}

</td>
</tr>
<tr>
<td valign="top">

ValueIsMissing

</td>
<td valign="top">

Value element is missing in KeyValueMapStepDefinition \{0\}

</td>
</tr>
</table>

