<!-- loiof87349e8b8e5435d87e93295dd29855c -->

# Additional Metadata to Support Edge Integration Cell

You need to add additional metadata when you develop custom sender adapters with the intention to deploy them on Edge Integration Cell.

If you'd like to use a sender adapter on an Edge Integration Cell runtime, add the following additional metadata.

> ### Note:  
> We assume that the address of a sender adapter deployed on Edge Integration Cell is composed in the following way:
> 
> <code>&lt;address of Edge Integration Cell runtime in private customer landscape&gt;/&lt;BasePath&gt;/&lt;endpoint&gt;</code>

Specify the `BasePath` as part of the `AdditionalMetadata` element like below:

```
<Metadata>
    <AdditionalMetadata>
        <Name>BasePath</Name>
        <Value>adapterInstanceID</Value>
        <GuiLabels>
            <Label language="en"/>
        </GuiLabels>
    </AdditionalMetadata>
</Metadata>
```

Add the following additional `AttributeMetadata` elements.

There are three different attribute types.

**Attribute Metadata**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

AttributeType

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies attribute type for additional metadata for Edge Integration Cell.

There are the following attribute types:

-   `Endpoint`

    Use this attribute type to specify the endpoint of the adapter.

    Example how to specify the `Endpoint` attribute in an `AttributeMetadata` element:

    ```
    <AttributeMetadata>
        <Name>endpointUrl</Name>
        <Usage>true</Usage>
        <DataType>xsd:string</DataType>
        <Default></Default>
        <Length></Length>
        <isparameterized>true</isparameterized>
        <AttributeType>Endpoint</AttributeType>
        <GuiLabels guid="ab1c2d3f-4ba5-6cde-78f9-x98765zz">
            <Label language="EN">Address</Label>
            <Label language="DE">Address</Label>
        </GuiLabels>
    </AttributeMetadata>
    
    ```

-   `AuthenticationType`

    Use this attribute type to specify the authentication option offered by the adapter.

    For the `Value` element, you can specify one of the following values:

    -   `NoAuthorization`

    -   `RoleBased` for role-based authentication


-   `RoleName`

    Use this attribute type to specify the role name to be specified when configuring the adapter.

    For adapters with role-based authentication, you must specify a role name.




</td>
</tr>
</table>

