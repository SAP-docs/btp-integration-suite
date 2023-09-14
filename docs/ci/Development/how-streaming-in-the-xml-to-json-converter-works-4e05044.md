<!-- loio4e05044231654134a7d19f4dded517e6 -->

# How Streaming in the XML-to-JSON Converter Works

During streaming the XML document is processed in parts or segments:

The individual tags of an XML document are processed consecutively,irrespective of where in the overall structure the tag occurs and how often \(multiplicity\). This means that during the streaming process the converter cannot *know* if an element occurs in the structure more than once. In other words, during the streaming process the object model that reflects the overall structure of the XML document \(and, therefore, also all information that can only be derived from the object model, like the multiplicity of elements\) is not in place. This is different to the non-streaming case, where the converter can calculate the multiplicity of the XML elements from the object model of the complete XML document. The multiplicity is needed to create a correct JSON document. Elements whose multiplicity is greater than one must be transformed to a JSON member with an array. For example, you may think that for the XML document `<root><B>b1</B><B>b2</B></root>`, you create the JSON document `{“root”:{“B”:”b1”,”B”:”b2”}}`. However, this JSON document is invalid, because the member name `“B”` occurs twice on the same hierarchy level.

To ensure nevertheless a conversion that creates correct JSON documents during streaming, you need to either manually provide the information about which XML elements are multiple in advance, or decide that every XML element is converted to a JSON array \(when configuring the converter in the Integration Designer\).

To illustrate this behavior, let’s consider how the following simple XML structure has to be converted to JSON:

```
<root>
  <A>a</A>
  <B>b1</B>
  <B>b2</B>
  <C>c</C>
</root>
```

Note that the element `root/B` occurs twice \(multiplicity = 2\).

Without streaming, the converter would produce the following JSON structure:

`{"root":{"A":"a","B":["b1","b2"],"C":"c"}}`

As expected, the XML element `root/B` would transform into a JSON member with an array as value, where the array has two values \(`b1` and `b2`\) – according to the multiplicity of `root/B`. Note that a JSON array is indicated by the following type of brackets: \[ … \].

With streaming with all elements to JSON arrays, the converter would produce the following JSON structure:

`{"root":[{"A":["a"],"B":["b1","b2"],"C":["c"]}]}`

All XML elements are transformed into members with a JSON array as value.

With streaming and specific elements as arrays \(where root/A and root/B are specified\), the converter would produce the following JSON structure:

`{"root":{"A":["a"],"B":["b1","b2"],"C":"c"}}`

An array is produced only for the XML elements root/A and root/B, but not for root/C.

With streaming and specific elements as arrays \(where only root/A is specified\), the converter would produce the following invalid JSON structure:

`{"root":{"A":["a"],"B":"b1",”B”:"b2","C":"c"}}`

