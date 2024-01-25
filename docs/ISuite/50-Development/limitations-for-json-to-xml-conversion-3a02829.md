<!-- loio3a02829ea84e4f7dac62bdd10d06b084 -->

# Limitations for JSON to XML Conversion

To ensure a successful conversion frrm JSON to XML format you have to know the limitations for this conversion.

The JSON to XML conversion has the following limitations:

-   The XML element and attribute names must not contain any delimiter characters, because the delimiter is used in JSON to separate the prefix from the element name.
-   Elements with mixed content are not supported.
-   Conversion of "@attr":null to XML is not supported. You get a NullPointerException; as of cluster version 1.21 you get a JsonXmlException.

-   JSON member names must not contain in their local or prefix part any characters that are not allowed for XML element/attribute names \(for example, space or column \(':'\) are not allowed\). XML element/attribute names are of type NCName \(see [http://www.w3.org/TR/1999/REC-xml-names-19990114/\#NT-NCName](http://www.w3.org/TR/1999/REC-xml-names-19990114/#NT-NCName)\).

-   JSON texts that start with an array \(for example, `[{"a":{"b":"bvalue"}}]` \) are not supported. The JSON text must start with a JSON object such as `{{"a":{"b":"bvalue"}}}`. A javax.xml.stream.XMLStreamException is thrown. As of cluster version 1.21, a JsonXmlException is thrown.

-   The root JSON object must contain exactly one member. If the root JSON object contains more than one member \(for example, `{"a":"avalue","b":"bvalue"}`\), a javax.xml.stream.XMLStreamException is thrown. If the root JSON object is empty \(`{}`\), a javax.xml.stream.XMLStreamException is thrown. As of cluster version 1.21, a JsonXmlException or IllegalStateException \(for `{}`\) is thrown.

    > ### Tip:  
    > If you need to convert a JSON file that doesn't fulfil this requirement, you can do the following:
    > 
    > Add a content modifier before the JSON to XML converter that changes the message body. In the entry field in tab *Message Body*, enter:
    > 
    > `{"root": ${in.body}}`

-   If no XML namespace is defined for a JSON prefix, the full member name with the prefix and JSON delimiter is set as the element name: "p:A" -\> <p:A\>.

-   If a JSON member name can't be converted into a valid XML namespace prefix and valid XML element or attribute name, a `JsonXmlException` is thrown.

    Example: If the JSON member name contains characters that are not allowed in an XML namespace prefix or XML name, an exception is thrown.

    In order to enable Cloud Integration to convert JSON content into valid XML, the JSON member names must follow the following naming rules:

    -   Names must start with a letter or underscore \(`_`\).

    -   Names can't start with the letters `xml` \(or `XML`, or `Xml`, and so forth\).

    -   Names can contain letters, digits, hyphens \(`-`\), underscores \(`_`\), and periods \(`.`\).


    For the exact rules refer to the XML specification: [https://www.w3.org/TR/2008/REC-xml-20081126/\#NT-NameChar](https://www.w3.org/TR/2008/REC-xml-20081126/#NT-NameChar)

    Examples for not allowed characters:

    `>`

    `<`

    `&`


See also: [3112970 - JSON-to-XML Converter Exception Caused by Invalid JSON Member Name](https://launchpad.support.sap.com/#/notes/3112970) \(Knowledge Base Article\)

**Related Information**  


[Define JSON to XML Converter](define-json-to-xml-converter-5a7c0cd.md "The JSON to XML converter enables you to transform messages in JSON format to XML format.")

[Conversion Rules for JSON to XML Conversion](conversion-rules-for-json-to-xml-conversion-232a9cf.md "To ensure a successful conversion of you data, you should make yourself familiar with the conversion rules.")

