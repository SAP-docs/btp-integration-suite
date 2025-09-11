<!-- loio2e04b9373d7e4908936a6c219e012d3c -->

# XML Threat Protection

An XML Threat Protection policy safeguards XML-based applications and APIs from malicious attacks. It enforces rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.

**Policy Settings**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Descriptions

</th>
</tr>
<tr>
<td valign="top" colspan="2">

General

</td>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

The unique name of the policy within the API artifact. Each policy in an API artifact must have a unique name to prevent naming conflicts.

</td>
</tr>
<tr>
<td valign="top">

On Error

</td>
<td valign="top">

Determines the behavior when an exception or an error occurs during the policy execution. The default value is abort on error.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

**Structure Check** 

</td>
</tr>
<tr>
<td valign="top">

Maximum Depth

</td>
<td valign="top">

Refers to the maximum allowed levels of nested XML elements \(or nodes\) from the root to the deepest child. The maximum value is 40,000.

For example, if the depth is set to 5, there can be no more than 5 levels of nested elements.

```
<!-- policy configuration having maximum node depth of 5-->
<root>
    <depth2>
        <depth3>
            <depth4>
                <depth5>
                    <depth6>Value A - Depth 6 <!-- this node exceeds the depth limit and will result in an invalid payload--></depth6>
                </depth5>
            </depth4>
        </depth3>
    </depth2>
    <depth2>
        <depth3>
            <depth4>
                <depth5>Value B - Depth 5 <!-- this node is within the limits--></depth5>
            </depth4>
        </depth3>
    </depth2>
</root>
```



</td>
</tr>
<tr>
<td valign="top">

Maximum Child Count per Element

</td>
<td valign="top">

The maximum number of child elements \(or nodes\) that can be present within a specific XML element. The maximum value is 1,00,000.

This is a measure to prevent excessive nesting or unreasonably large XML structures, which could be exploited in certain types of attacks, such as denial-of-service \(DoS\) attacks or resource exhaustion.

</td>
</tr>
<tr>
<td valign="top">

Maximum Attribute per Element

</td>
<td valign="top">

The maximum number of attributes an individual XML element can contain. The maximum value is 50,000.

This setting ensures that XML documents are not overly complex and are within manageable limits, reducing the risk of attacks or performance issues.

</td>
</tr>
<tr>
<td valign="top">

Maximum Namespace per Element

</td>
<td valign="top">

The maximum number of XML namespaces that can be associated with a single XML element. The maximum value is 25,000.

For example, the `department` element in your XML has four namespaces declared: `ns1`, `ns2`, `ns3`, and `ns4`, each associated with different department like sales, marketing, finance, and operations, respectively. If the **Max Namespace per Element** setting is set to 3, this document would violate the policy because the `department` element is using 4 namespaces, exceeding the allowed limit.

```
<!-- policy configuration having maximum namespace count as 3-->
<parent>
    <child xmlns:ns1="https://example.com" xmlns:ns2="https://example.com/ns2" xmlns:ns3="https://example.com/ns3" xmlns:ns4="https://example.com/ns4">
        <!-- this element is invalid since there are 4 namespaces defined-->
    </child>
    <child xmlns:ns1="https://example.com" xmlns:ns2="https://example.com/ns2" xmlns:ns3="https://example.com/ns3" ns3:attr1="value1">
        <!-- this will not fail as there are 3 namespaces defined and the 4th one is an attribute which has been associated with a namespace. This attribute will be counted in the attributeCount parameter since this is technically an attribute and not a namespace-->
    </child>
</parent>
```



</td>
</tr>
<tr>
<td valign="top">

Maximum XML Payload Size \(KB\)

</td>
<td valign="top">

The maximum size limit for an XML payload is specified in kilobytes \(KB\), based on the total number of kilobytes the document contains.

> ### Note:  
> If this field is left empty, a system-enforced runtime limit of 10,000 KB \(where 1 KB = 1000 bytes\) will apply.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

**Length Check** 

</td>
</tr>
<tr>
<td valign="top">

Element Name Character Limit

</td>
<td valign="top">

Defines a limit on the maximum number of characters allowed in any element name within the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Attribute Name Character Limit

</td>
<td valign="top">

Defines a limit on the maximum number of characters allowed in any attribute name within the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Namespace Prefix Character Limit

</td>
<td valign="top">

Defines a limit on the maximum number of characters allowed in the namespace prefix within the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Processing Instructions Target Character Limit

</td>
<td valign="top">

Defines a limit on the maximum number of characters allowed in the target length of any processing instruction present in the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Text Character Limit

</td>
<td valign="top">

Defines a character limit for any text present between two adjacent element in the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Attribute Value Character Limit

</td>
<td valign="top">

Defines a character limit for any attribute values present between any two element nodes in the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Namespace URL Character Limit

</td>
<td valign="top">

Defines a character limit for any namespace URIs present in the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Comment Character Limit

</td>
<td valign="top">

Defines a character limit for any comments present in the XML document. The maximum value is 10,00,000.

</td>
</tr>
<tr>
<td valign="top">

Processing Instructions Value Character Limit

</td>
<td valign="top">

Defines a limit on the maximum number of characters allowed in the value length of any processing instruction present in the XML document. The maximum value is 10,00,000.

</td>
</tr>
</table>

> ### Note:  
> Apart from the **Name** and **On Error** fields \(which are generic\), if you leave the other fields empty, no validation is performed for those fields.

> ### Note:  
> When the API validation policy is modeled inside a reusable API, the schema validation is performed against the API specification of the consuming API. This applies if you intend to deploy the API artifact with the validation policy on the Edge Integration Cell runtime.

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth.")

[Authorization](authorization-6658409.md "This policy evaluates whether a user should be permitted to access a protected API.")

[JSON Threat Protection](json-threat-protection-c4991a6.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

[API Validation](api-validation-02ff41b.md "The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.")

