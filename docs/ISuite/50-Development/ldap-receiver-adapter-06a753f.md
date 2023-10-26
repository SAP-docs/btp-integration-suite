<!-- loio06a753f90fd64272af1692603cdd3b9e -->

# LDAP Receiver Adapter

The Lightweight Directory Access Protocol \(LDAP\) Receiver Adapter enables you to communicate with systems that expose data through LDAP service.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

In case you've input messages in different formats, you need to use a mapping step to create a target payload that can be recognized by the LDAP receiver adapter. You can use this schema as a template for the target in mapping step.

```
<?xml version="1.0" encoding="UTF-8"?>
<schema xmlns="http://www.w3.org/2001/XMLSchema">
    <element name="Schema">
        <complexType>
            <sequence>
            <element name="DistinguishedName" maxOccurs="1" minOccurs="1" type="string"/>
            <element name="ObjectClass" maxOccurs="1" minOccurs="0" type="string"/>
                <element name="Attributes" maxOccurs="1" minOccurs="1">
                    <complexType>
                        <sequence>
                            <element name="cn" type="string" maxOccurs="1" minOccurs="0"></element>
                            <element name="sAMAccountName" type="string" maxOccurs="1" minOccurs="1"></element>
                            <element name="sn" type="string" maxOccurs="1" minOccurs="0"></element>
                            <element name="givenName" type="string" maxOccurs="1" minOccurs="0"></element>
                            <element name="displayName" type="string" maxOccurs="1" minOccurs="0"></element>
                            <element name="name" type="string" maxOccurs="1" minOccurs="0"></element>
                        </sequence>
                    </complexType>
                </element>
            </sequence>
        </complexType>
    </element>
</schema>

```

> ### Note:  
> -   You can't update multiple records in a single processing cycle. You can only perform a given operation on 1 record at a time.
> 
> -   You can update attribute with multiple values.

> ### Remember:  
> You must use *SAP Cloud Connector* for connecting to an LDAP service using the LDAP adapter. LDAP adapter supports version 2.9 or higher versions of the cloud connector.
> 
> For more information on using the *SAP Cloud Connector*, see the [official documentation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html).

Once you've created a receiver channel and selected the LDAP Receiver Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).



<a name="loio06a753f90fd64272af1692603cdd3b9e__section_ns2_kd2_hqb"/>

## LDAP Adapter Configurations

Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Enter the URL of the LDAP directory service that you're connecting to.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select the proxy type that you want to use. Currently, only *On Premise* is supported.

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

</td>
<td valign="top">

Enter the location ID.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication type that you want to use. Currently, only *Simple* is supported.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Enter the credential name you've deployed in the tenant.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation that you want to perform. The supported operations are:

-   *Insert*: Allows you to create a new entry in LDAP service.

-   *Modify*: Use this operation to edit an existing entry in LDAP directory.

-   *Search*: This operation allows you to perform a query for entries in the LDAP directory. The retrieved data is either in Java \(JNDI\) Attributes or XML format.

    To know more about the search operation, read the [blog](https://blogs.sap.com/2020/01/24/search-operation-in-ldap-adapter-in-sap-cloud-platform-integration/).

-   *Delete*: Erases an entry from the LDAP directory.




</td>
</tr>
</table>



### *Insert*

Select the *Input Type* that you're providing. Supported types are: *Java \(JNDI\) Attributes* and *XML*.



### *Delete*

Provide the *Distinguished Name* of the objectClass that you want to delete.



### *Modify*

**Modify**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Input Type*

</td>
<td valign="top">

Select the *Input Type that* you're providing. Supported types are:

-   *Java \(JNDI\) Attributes*

-   *XML*




</td>
</tr>
<tr>
<td valign="top" colspan="2">

For *Java \(JNDI\) Attributes*, select one of the following:

</td>
</tr>
<tr>
<td valign="top">

*Consider attributes from class ModificationItem*

</td>
<td valign="top">

Enable the checkbox to have the script file return '*<modificationItem\>*' object in body having *<ModificationItem\[\]\>*.

</td>
</tr>
<tr>
<td valign="top">

*Modification Type*

</td>
<td valign="top">

Select the type of modification that you want to make. Supported types are:

-   Add

-   Remove

-   Replace




</td>
</tr>
<tr>
<td valign="top" colspan="2">

For *XML*, do the following:

</td>
</tr>
<tr>
<td valign="top">

*Modification Type*

</td>
<td valign="top">

Select the type of modification that you want to make. Supported types are:

-   Add

-   Remove

-   Replace




</td>
</tr>
<tr>
<td valign="top">

*Consider additional attributes for modification*

</td>
<td valign="top">

Enable checkbox to pick up modification item from the XML attribute '*<modificationType\>*'. This XML Attribute is allowed to have 3 values – add, remove, and replace.

> ### Example:  
> <proxyAddresses modificationType='add'\>john\_doe@gmail.com</proxyAddresses\>
> 
> <proxyAddresses modificationType='remove'\>doe\_john@gmail.com</proxyAddresses\>



</td>
</tr>
</table>



### *Search*

**Search**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Base DN*

</td>
<td valign="top">

Provide the Base Distinguished Name that helps to identify the highest point in the hierarchy of the directory from which the search is initiated.

</td>
</tr>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Select an attribute, placed below the Base DN, to define the extent of the search and the attributes are:

-   Object

-   One Level

-   Subtree




</td>
</tr>
<tr>
<td valign="top">

*Search Filter*

</td>
<td valign="top">

Specify a search criteria applied to each entry within the scope.

> ### Example:  
> -   \(&\(mail=\*.gmail.com\)\(objectClass=user\)\)
> 
> -   \(sAMAccountType=805306368\)



</td>
</tr>
<tr>
<td valign="top">

*Output Type*

</td>
<td valign="top">

Select the type of output format when the data is returned.

</td>
</tr>
<tr>
<td valign="top">

*Multivalued Response*

</td>
<td valign="top">

Select the format for your responses if there are multiple values for the queried attribute. Supported response types are:

-   *As XML tags*

    > ### Example:  
    > <proxyAddresses\>john\_doe@gmail.com</proxyAddresses\>
    > 
    > <proxyAddresses\>doe\_john@gmail.com</proxyAddresses\>

-   *Semicolon separated*

    > ### Example:  
    > <proxyAddresses\>john\_doe@gmail.com;doe\_john@gmail.com</proxyAddresses\>




</td>
</tr>
<tr>
<td valign="top">

*Attributes*

</td>
<td valign="top">

Specify the attribute that the query has to return.

> ### Example:  
> cn, sAMAccountName,sn,givenName



</td>
</tr>
<tr>
<td valign="top">

*Size Limit*

</td>
<td valign="top">

Define an integer value, to set the maximum number of entries that is returned.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in min\)*

</td>
<td valign="top">

Define an integer value, to set the maximum time that the server must wait before returning the results.

</td>
</tr>
</table>

