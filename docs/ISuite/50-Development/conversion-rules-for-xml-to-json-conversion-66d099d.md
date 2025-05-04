<!-- copy66d099d0014842299fc91ee5876717a4 -->

# Conversion Rules for XML to JSON Conversion

To ensure a successful conversion from XML format to JSON format, you should make yourself familiar with the conversion rules.

The conversion from XML format to JSON format follows the following rules:

-   An element is represented as JSON member whose name is the concatenation of JSON prefix corresponding to the XML namespace, JSON delimiter, and the element name. If the element has no namespace, no prefix and JSON delimiter is added to the JSON name.

-   JSON members whose names start with `‘@’` are transformed to XML attributes. For example, if the member name is `“@pre1.attr1”`, if the JSON delimiter is `‘.’` and if there is a JSON prefix to namespace mapping `“pre1”` to `“https://test.com/”`, then an XML attribute with local name `“attr1”` and namespace `“https://test.com/”` is created.

    JSON members whose name start with `‘@’` must appear at the beginning of the child members of the parent member, for example:

    > ### Sample Code:  
    > ```
    > {"parent":{
    >     "@attr1":123,
    >     "@attr2":1234,
    >     "id": "000039002",
    >     "href": "",
    >     "externalId": "Test_3"
    >     }
    > }
    > 
    > ```

    This representation can be transformed because the `“@attr1”` and `“@attr2”` members appear at the beginning of the child members of the “parent” member. The following example would result in the error "Trying to write an attribute when there is no open start element" because the `“@attr1”` and `“@attr2”` child members do not appear at the beginning of the child members of the “parent” member:

    > ### Sample Code:  
    > ```
    > {"parent":{
    >     "id": "000039002",
    >    "@attr1":123,
    >     "href": "",
    >      “@attr2”:1234,
    >     "externalId": "Test_3"
    >     }
    > }
    > 
    > ```

    If your JSON file starts with a member whose name starts with `‘@’`, the converter throws the following error message:

    `The root member name starts with the attribute indicator @. An attribute cannot be root.`

    This error is also raised, if you've chosen the option *Add XML Root Element*.

    Example JSON file:

    > ### Sample Code:  
    > ```
    > {
    >     "@attr1":123,
    >     "test":1234,
    >     "id": "000039002",
    >     "href": "",
    >     "externalId": "Test_3"
    > }
    > 
    > ```

-   An element with no characters or child elements is represented by `"element" : ""` 

-   An element with multiple child elements of the same name is represented by an array. This also holds if between the children with the same name other children with another name reside.

    Example: `<root><childA>A1</childA><childB>B</childB><childA>A2</childA></root>` is transformed in the non-streaming case to `{"root":{"childA":["A1","A2"],"childB":"B"}}`, which means that the order of the children is not preserved.

    In the streaming case, the result is: `{"root":{"childA":["A1"],"childB":"B","childA":["A2"]"}}`, which means that a non-valid JSON document is created because the member `"childA"`appears twice.

-   The value of a complex element \(having attributes for example\) is represented by a separate member `"$":"value"`.

-   Elements with mixed content \(for example. `<A>mixed1_value<B>valueB</B>mixed2_value</A>`\) are not supported. Currently you get wrong results for XML to JSON: `{"A":{"B":"valueB","$":"mixed1_valuemixed2_value"}}` in the non-streaming case or `{"A":"$":mixed1_value","B":"valueB","$":"mixed2_value"}}` in the streaming case.

-   All element/attribute values are transformed to JSON string.

-   No namespace declaration is written into the JSON document.

-   Tabs, spaces, new lines between elements and attributes are ignored. However, a white space value of an element with simple type is represented in JSON; example `<A> </A>` is represented by `"A":" "`.

-   If you have an element with namespace but without XML prefix whose namespace is not contained in the XML-namespace-to-Json-prefix map, then you get an exception: `<A xmlns="http://test"/>` leads to `IllegalStateException Invalid JSON namespace: http://test`.

    This is not the case if you choose the streaming option. With streaming the namespace is just ignored: `<A xmlns="http://test"/>v</A>` leads to `{"A":"v"}`.

-   If you have an element with namespace and XML prefix whose namespace is not contained in the XML-namespace-to-Json-prefix map then the XML prefix is used as JSON prefix `<ns:A xmlns:ns:="http://test"/>` leads to `"ns.A":""` \(if JSON delimiter is `'.'`\).


**Related Information**  


[Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md "The XML to JSON converter enables you to transform messages in XML format to JSON format.")

[How Streaming in the XML-to-JSON Converter Works](how-streaming-in-the-xml-to-json-converter-works-4e05044.md "During streaming the XML document is processed in parts or segments:")

[Limitations for XML-to-JSON Conversion](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a5b4641c393f406bb544987497c90a72.html "To ensure a successful conversion form XML to JSON format you have to know the limitations for this conversion.") :arrow_upper_right:

 <?sap-ot O2O class="- topic/link " href="e8e0fff0280c4ddb8359e198a2c20c8c.xml" text="" desc="" xtrc="link:4" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/66d099d0014842299fc91ee5876717a4.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

