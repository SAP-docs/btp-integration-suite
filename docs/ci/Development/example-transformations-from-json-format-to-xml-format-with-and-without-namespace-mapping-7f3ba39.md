<!-- loio7f3ba399cc3541a792075732ab5990a3 -->

# Example: Transformations from JSON format to XML format with and without Namespace Mapping

Whether you select the option *Use Namespace Mapping* or not, leads to different transformation results.



<a name="loio7f3ba399cc3541a792075732ab5990a3__section_csh_w5t_cz"/>

## Using Namespace Mapping

For this example we look at the following **JSON document**:

```
{"abc:A":{"xyz:B":{"@xyz:attr1":"1","@attr2":"2","$":"valueB"},"C":["valueC1","valueC2"],"D":"","E":"valueE"}}
```

For the transformation of this document we choose the following settings:

-   The character ':' is used as the JSON prefix separator.

-   The option *Use Namespace Mapping* is selected.

-   The JSON-prefix-to-XML-namespace mapping is as follows:


    <table>
    <tr>
    <th valign="top">

    JSON Prefix
    
    </th>
    <th valign="top">

    XML Namespace
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    abc
    
    </td>
    <td valign="top">
    
    http://com.sap/abc
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    xyz
    
    </td>
    <td valign="top">
    
    http://com.sap/xyz
    
    </td>
    </tr>
    </table>
    

We get the following XML document:

```

					<?xml version='1.0' encoding='UTF-8'?>
					<abc:A xmlns:abc="http://com.sap/abc" xmlns:xyz="http://com.sap/xyz"><xyz:B xyz:attr1="1" attr2="2">valueB</xyz:B><C>valueC1</C><C>valueC2</C><D/><E>valueE<E></abc:A>
				
```



<a name="loio7f3ba399cc3541a792075732ab5990a3__section_a1r_q5t_cz"/>

## No Namespace Mapping

For this example we look at the following **JSON document**:

```
{"abc.A":{"xyz.B":{"@xyz.attr1":"1","@attr2":"2","$":"valueB"},"C":["valueC1","valueC2"],"D":"","E":"valueE"}}
```

For the transformation of this document we choose the following settings:

-   The character ':' is used as the JSON prefix separator.

-   The option *Use Namespace Mapping* is **not** selected.


We get the following**XML document**:

```
<?xml version='1.0' encoding='UTF-8'?><A><B attr1="1" attr2="2">valueB</B><C>valueC1</C><C>valueC2</C><D/><E>valueE<E></A>
```

