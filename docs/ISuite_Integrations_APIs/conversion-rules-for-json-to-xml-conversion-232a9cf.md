<!-- loio232a9cf5194d40189a3672a0ef1567c1 -->

# Conversion Rules for JSON to XML Conversion

To ensure a successful conversion of you data, you should make yourself familiar with the conversion rules.

The conversion from JSON format to XML format follows the following rules:

-   The value of a complex element \(having attributes for example\) is represented by a separate member `"$":"value"`.

-   An element with multiple child elements of the same name is represented by an array. This also holds if between the children with the same name other children with another name reside.

    Example: `<root><childA>A1</childA><childB>B</childB><childA>A2</childA></root>` is transformed in the non-streaming case to `{"root":{"childA":["A1","A2"],"childB":"B"}}`, which means that the order of the children is not preserved.

    In the streaming case, the result is: `{"root":{"childA":["A1"],"childB":"B","childA":["A2"]"}}`, which means that a non-valid JSON document is created because the member `"childA"`appears twice.

-   An element with no characters or child elements is represented by `"element" : ""` 

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

-   An element is represented as JSON member whose name is the concatenation of JSON prefix corresponding to the XML namespace, JSON delimiter, and the element name. If the element has no namespace, no prefix and JSON delimiter is added to the JSON name.

-   A member with JSON null value is transformed to empty element; example: `"C":null` is converted to `<C/>`.

-   Conversion of `"@attr":null` to XML is not supported \(you get a NullPointerException, since cluster version 1.21 you get a JsonXmlException\).

-   The result XML document is encoded in UTF-8 and gets the XML header `"<?xml version='1.0' encoding='UTF-8'?>"`.

-   The content of the XML-Namespace-to-JSON-Prefix map is transformed to namespace prefix declarations on the root element.

-   If for a JSON prefix no XML Namespace is defined, then the full member name with the prefix and JSON delimiter is set as element name: `"p.A"` leads to `<p.A>`.


**Related Information**  


[Define JSON to XML Converter](define-json-to-xml-converter-5a7c0cd.md "The JSON to XML converter enables you to transform messages in JSON format to XML format.")

