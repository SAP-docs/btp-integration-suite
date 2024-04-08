<!-- loio8827f9feb94e4264aaf42ac1c6ce11b7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Content Enricher



## Context

The content enricher adds the content of a payload with the original message in the course of an integration process. This process converts the two separate messages into a single enhanced payload. This feature enables you to make external calls during the course of an integration process to obtain additional data, if any.

> ### Tip:  
> To find out how to use this step in a dedicated scenario, check out the design guideline [Content Enricher](content-enricher-0e7ba7f.md).

Consider the first message in the integration flow as the original message and the message obtained by making an external call during the integration process as the lookup message. You can choose between two strategies to enrich these two payloads as a single message:

-   Combine
-   Enrich

Consider the following original and lookup messages.

**Original Message**

```
<EmployeeList>
       <Employee>
              <id>111</id>
              <name>Santosh</name>
              <external_id>ext_111</external_id>
       </Employee>
       <Employee>
              <id>22</id>
              <name>Geeta</name>
              <external_id>ext_222</external_id>
       </Employee>
</EmployeeList>

```

**Lookup Message**

```
<EmergencyContacts>
       <contact>
              <c_id>1</c_id>
              <c_code>ext_111</c_code>
              <isEmergency>0</isEmergency>
              <phone>9999</phone>
              <street>1st street</street>
              <city>Gulbarga</city>
       </contact>
       <contact>
              <c_id>2</c_id>
              <c_code>ext_111</c_code>
              <isEmergency>1</isEmergency>
              <phone>1010</phone>
              <street>23rd Cross</street>
              <city>Chitapur</city>
       </contact>
       <contact>
              <c_id>3</c_id>
              <c_code>ext_333</c_code>
              <isEmergency>1</isEmergency>
              <phone>007</phone>
              <street></street>
              <city>Raichur</city>
       </contact>
</EmergencyContacts>


```

If you use *Combine* as the aggregation strategy, the enriched message appears in the following format.

**Enriched Message**

```
<multimap:messages xmlns:multimap=”http://sap.com/xi/XI/SplitAndMerge”>
<message1>
<EmployeeList>
       <Employee>
              <id>111</id>
              <name>Santosh</name>
              <external_id>ext_111</external_id>
       </Employee>
       <Employee>
              <id>22</id>
              <name>Geeta</name>
              <external_id>ext_222</external_id>
       </Employee>
</EmployeeList>
</message1>
<message2>
<EmergencyContacts>
       <contact>
              <c_id>1</c_id>
              <c_code>ext_111</c_code>
              <isEmergency>0</isEmergency>
              <phone>9999</phone>
              <street>1st street</street>
              <city>Gulbarga</city>
       </contact>
       <contact>
              <c_id>2</c_id>
              <c_code>ext_111</c_code>
              <isEmergency>1</isEmergency>
              <phone>1010</phone>
              <street>23rd Cross</street>
              <city>Chitapur</city>
       </contact>
       <contact>
              <c_id>3</c_id>
              <c_code>ext_333</c_code>
              <isEmergency>1</isEmergency>
              <phone>007</phone>
              <street></street>
              <city>Raichur</city>
       </contact>
</EmergencyContacts>
</message2>
</multimap:messages xmlns:multimap=”http://sap.com/xi/XI/SplitAndMerge”>

```

*Enrich* offers you control on how you can merge the original and lookup message. In this example, we consider the node <ext\_111\> as the reference to enrich the original message with the lookup message.

Consequently, you specify the following values while configuring the Content Enricher.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Field

</th>
<th valign="top">

User input

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Original Message

</td>
<td valign="top">

Path to Node

</td>
<td valign="top">

EmployeeList/Employee

</td>
</tr>
<tr>
<td valign="top">

Key Element

</td>
<td valign="top">

external\_id

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Lookup Message

</td>
<td valign="top">

Path to Node

</td>
<td valign="top">

EmergencyContacts/contact

</td>
</tr>
<tr>
<td valign="top">

Key Element

</td>
<td valign="top">

c\_code

</td>
</tr>
</table>

The enriched message is in the following format.

```
<EmployeeList>
       <Employee>
              <id>111</id>
              <name>Santosh</name>
              <external_id>ext_111</external_id>
              <contact>
                     <c_id>1</c_id>
                     <c_code>ext_111</c_code>
                     <isEmergency>0</isEmergency>
                     <phone>9999</phone>
                     <street>1st street</street>
                     <city>Gulbarga</city>
              </contact>
              <contact>
                     <c_id>2</c_id>
                     <c_code>ext_111</c_code>
                     <isEmergency>1</isEmergency>
                     <phone>1010</phone>
                     <street>23rd Cross</street>
                     <city>Chitapur</city>
              </contact>
       </Employee>
       <Employee>
              <id>22</id>
              <name>Geeta</name>
              <external_id>ext_222</external_id>
       </Employee>
</EmployeeList>

```

> ### Remember:  
> Content Enricher doesn't support an XML payload that contains namespace-oriented attributes in its XML elements.
> 
> For example, the XML element *<mail xsi:nil=true/\>* isn't supported because the attribute *<nil\>* has a namespace prefix. But the XML element *<mail nil=true/\>* works as expected.

> ### Remember:  
> If lookup message contains more than one entry of the key element, content enricher enhances the enriched message with all the entries referred by the key element in lookup message. In the preceding example, the lookup message contains the key element `ext_111` in two places. You can see that the enriched message contains both the `<contact>` entries that the key element refers to.

> ### Note:  
> The *Enrich* strategy doesn't work as expected if:
> 
> -   The *Key Element* in the Lookup Message is an empty string.
> 
> -   The *Key Element* in the Original message can't be located during runtime.
> 
> 
> In such cases, the Content Enricher doesn't enrich the message.



## Procedure

1.  If you want to add a *Content Enricher* step to the integration process, perform the following substeps.

    1.  In the palette, choose ![](images/external_call_bfbf8b0.png) \(Call\) and then choose :envelope::gear:

    2.  Place the *Content Enricher* shape in the integration process and define message path.


2.  Select the *Content Enricher*.

3.  In the *Processing* tab, select an option for parameter *Aggregation Algorithm*.

    There are the following options.


    <table>
    <tr>
    <th valign="top">

    Value
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Combine* 
    
    </td>
    <td valign="top">
    
    Combines the original and lookup messages. You can't define any rules for combining messages.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Enrich* 
    
    </td>
    <td valign="top">
    
    You can define the path to node and key element based on which the original message is enriched with the lookup message.
    
    </td>
    </tr>
    </table>
    
4.  If you've selected *Enrich* as the *Content Enrichment Type*, provide values in fields based on description in table.


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    Original Message
    
    </td>
    <td valign="top">
    
    Path to Node
    
    </td>
    <td valign="top">
    
    Path to the reference node in the original message
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Element
    
    </td>
    <td valign="top">
    
    Key element in the original message
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    Lookup Message
    
    </td>
    <td valign="top">
    
    Path to Node
    
    </td>
    <td valign="top">
    
    Path to the reference node in the lookup message
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Element
    
    </td>
    <td valign="top">
    
    Key element in the lookup message
    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.


