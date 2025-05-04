<!-- copy4bf5a05cad514218a3a986531ada30b6 -->

# Limitations for XML-to-JSON Conversion

To ensure a successful conversion form XML to JSON format you have to know the limitations for this conversion.

The XML to JSON conversion has the following limitations:

-   The XML element and attribute names must not contain any delimiter characters, because the delimiter is used in JSON to separate the prefix from the element name.
-   Elements with mixed content are not supported.
-   XML comments \(<!-- comment --\>\) are not represented in the JSON document; they are ignored.
-   DTD declarations are not represented in the JSON document; they are ignored.
-   XML processing instructions are not represented in the JSON document; they are ignored.
-   No conversion to JSON primitive types for XML to JSON. All XML element/attribute values are transformed to a JSON string.
-   Entity references \(except the predefined entity references &amp; &lt; &gt; &quot; &apos;\) are not represented in the JSON document; they are ignored.
-   If a sibling with another name resides between XML sibling nodes with the same name, then the order of the siblings is not kept in JSON in the non-streaming case, because siblings with the same name are represented by one array. Example: `<root><childA>A1</childA><childB>B</childB><childA>A2</childA></root>` leads to `{"root":{"childA":["A1","A2"],"childB":"B"}}`.

    In the streaming case this leads to an invalid JSON document: `{"root":{"childA":["A1"],"childB":"B","childA":["A2"]}`.

-   If you have an element with a namespace but no XML prefix whose namespace is not contained in the XML-namespace-to-JSON-prefix map, you get an exception: <A xmlns="http://test"/\> -\> IllegalStateException Invalid JSON namespace: http://test.

    If you choose the streaming option, the namespace is ignored: `<A xmlns="http://test"/>v</A>` leads to `{"A":"v"}`.


**Related Information**  


[Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md "The XML to JSON converter enables you to transform messages in XML format to JSON format.")

[Conversion Rules for XML to JSON Conversion](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778aed733e3140cea0435f4615d53812.html "To ensure a successful conversion from XML format to JSON format, you should make yourself familiar with the conversion rules.") :arrow_upper_right:

[How Streaming in the XML-to-JSON Converter Works](how-streaming-in-the-xml-to-json-converter-works-4e05044.md "During streaming the XML document is processed in parts or segments:")

 <?sap-ot O2O class="- topic/link " href="e8e0fff0280c4ddb8359e198a2c20c8c.xml" text="" desc="" xtrc="link:4" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4bf5a05cad514218a3a986531ada30b6.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

