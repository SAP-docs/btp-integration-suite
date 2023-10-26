<!-- loio3018480fa8ba40a7a5eda8a21b11e67f -->

# Avoiding Encoding Issues

The integration runtime supports the following two kinds of \(internal\) data representations: binary data and string \(sequence of characters\). Conversions between these representations may cause issues that can result in erroneous message processing.

This topic lists the main measures to help you avoid any such issues.

The *Content Modifier* step provides the following options for configuring how data is to be encoded \(based on the `CamelCharsetName` element\):

-   Configuring the *Exchange Property* 

-   Configuring the *Message Header*




## General Recommendations

As far as applicable for your scenario, try to implement the following measures:

**Recommendations**


<table>
<tr>
<th valign="top">

Recommendation

</th>
<th valign="top">

Required Tasks

</th>
<th valign="top">

Conditions and Challenges

</th>
</tr>
<tr>
<td valign="top">

**Use UTF-8 character encoding only** 

Try to use UTF-8 encoding for all binary character representations throughout the scenario.

</td>
<td valign="top">

You do not have to set any `CamelCharsetName` property or header \(as UTF-8 is the default\), or any XML declaration \(as UTF-8 is also the default for XML\).

</td>
<td valign="top">

Make sure that all mappings use UTF-8 for output encoding. If you do not define an output encoding, UTF-8 is used as the default.

The challenge with this solution is that it requires all your communication partners to send and receive data in UTF-8 character encoding \(which, although not uncommon, is unfortunately not always the case\).

</td>
</tr>
<tr>
<td valign="top">

**Use a fixed character encoding throughout the whole integration flow**

If your communication partners require a character encoding for communication other than UTF-8 \(for example, ISO-8859-15\), and this character encoding is the same for all communication partners, you can set up your integration flow to use that character encoding.

</td>
<td valign="top">

Perform the following steps:

-   Set the `CamelCharsetName` exchange property to your character set.

-   Make sure that all your mappings have the required output. Make sure that you do not remove the XML declaration for binary XML representation as this could cause the parsing of binary XML content to fail.




</td>
<td valign="top">

The challenge with this solution is that if you have more than one communication partner, it is rather unlikely that they all agree on a character encoding different from UTF-8.

</td>
</tr>
<tr>
<td valign="top">

**Avoid binary-to-string conversions** 

</td>
<td valign="top">

If you are working with XML data and you are communicating with different communication partners using different character encodings, one way to avoid character encoding issues is to avoid the serialized string representation of XML documents altogether.

In this case, the content of the `CamelCharsetName` is irrelevant as no string-to-binary conversion occurs \(only XML parsing and marshaling\).

</td>
<td valign="top">

If using this solution, the integration flow developer must not modify a message body that contains an XML document with a content modifier or a string-based script.

The filter and XSLT mapping steps both have the option to provide string output. This option should only be used if the result is a non-XML string, not an XML document or fragment.

The integration developer must therefore exercise caution and due care if applying these measures.

</td>
</tr>
</table>

**Related Information**  


[Character Encodings: Background Information](character-encodings-background-information-083c971.md "")

