<!-- loio2430dd4217b04187950c16b5ec40b333 -->

# Example: Transformations from XML format to JSON format with and without Namespace Mapping

Whether you select the option *Use Namespace Mapping* or not, leads to different transformation results.



<a name="loio2430dd4217b04187950c16b5ec40b333__section_dsh_pwt_cz"/>

## Using Namespace Mapping



## Example

For this example we look at the following **XML document**:

```

					<?xml version='1.0' encoding='UTF-8'?>
					<n1:A xmlns:n1="http://com.sap/abc" xmlns:n2="http://com.sap/xyz">
					<n2:B n2:attr1="1" attr2="2">valueB</n2:B>
					<C>valueC1</C>
					<C>valueC2</C>
					<D/>
					<E>valueE<E>
					</n1:A>
				
```

For the transformation of this document we choose the following settings:

-   The character ':' is used as the JSON prefix separator.

-   The option *Use Namespace Mapping* is selected.

-   The XML-namespace-to-JSON-prefix mapping is as follows:


    <table>
    <tr>
    <th valign="top">

    XML Namespace
    
    </th>
    <th valign="top">

    JSON Prefix
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    http://com.sap/abc
    
    </td>
    <td valign="top">
    
    abc
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    http://com.sap/xyz
    
    </td>
    <td valign="top">
    
    xyz
    
    </td>
    </tr>
    </table>
    

We get the following **JSON document**:

```
{"abc:A":{"xyz:B":{"@xyz:attr1":"1","@attr2":"2","$":"valueB"},"C":["valueC1","valueC2"],"D":"","E":"valueE"}}
```

> ### Note:  
> Line breaks and spaces between the elements are ignored.



<a name="loio2430dd4217b04187950c16b5ec40b333__section_lcl_nxt_cz"/>

## No Namespace Mapping



## Example

For this example we look at the following **XML document**:

```

							<?xml version='1.0' encoding='UTF-8'?>
							<abc:A xmlns:abc="http://com.sap/abc" xmlns:xyz="http://com.sap/xyz"><xyz:B xyz:attr1="1" attr2="2">valueB</xyz:B><C>valueC1</C><C>valueC2</C><D/><E>valueE</E></abc:A>
						
```

For the transformation we choose the following settings:

-   The character ':' is used as the JSON prefix separator.

-   The option *Use Namespace Mapping* is **not** selected.


We get the following **JSON Document**:

```
{"A":{"B":{"@attr1":"1","@attr2":"2","$":"valueB"},"C":["valueC1","valueC2"],"D":"","E":"valueE"}}
```

