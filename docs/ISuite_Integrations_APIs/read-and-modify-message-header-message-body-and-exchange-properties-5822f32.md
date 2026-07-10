<!-- loio5822f320823040af915c54a379463547 -->

# Read and Modify Message Header, Message Body, and Exchange Properties

You can use the Script step to address \(get, add, modify, or delete\) the message header, the message body, and exchange properties, using the interface `Message` object.

For an overview of the data model and the message structure used by Cloud Integration, see [The Camel Data Model in a Nutshell](the-camel-data-model-in-a-nutshell-d4f8f03.md).

Note that data written to the message header during a processing step, for example, in a Content Modifier or Script step, also becomes part of the outbound message addressed to a receiver system. However, properties remain within the integration flow and are not handed over to receivers. Because of this, it is important to consider the following header size restriction if you are using an HTTP-based receiver adapter: If the message header exceeds a certain value, the receiver may not be able to accept the inbound call. This rule applies to all HTTP-based receiver adapters. The limiting value depends on the characteristics of the receiver system, but typically ranges between 4 and 16 KB. To overcome this issue, you can use a subsequent Content Modifier step to delete all headers that are not supposed to be part of the outbound message.

The following table provides examples showing how to use the Script step with this interface.

****


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

Example Requests / More Information

</th>
</tr>
<tr>
<td valign="top">

Address exchange properties

</td>
<td valign="top">

You can apply the following methods on an instance of `Message` in order to get or set exchange properties:

`getProperties()`

`getProperty(String name)`

`setProperty(String name, Object value)` 

The following Groovy Script reads two exchange properties \(`Property1` and `Property2`\), calculates the sum of their values, and stores the result in a third property \(`Property3`\):

```
def Message processData(Message message) {
    def Property1 = message.getProperty("Property1") as Double
    def Property2 = message.getProperty("Property2") as Double
    def Property3 = Property1 + Property2
    message.setProperty("Property3", Property3)
    return message;
}

```



</td>
</tr>
<tr>
<td valign="top">

Address the message header.

</td>
<td valign="top">

You can apply the following methods on an instance of `Message` in order to get or set message headers:

`getHeaders()`

`getHeader(String headerName, Class<T> headerType)` 

`setHeader(String name, Object value)` 

</td>
</tr>
<tr>
<td valign="top">

Address message body

</td>
<td valign="top">

You can apply the following methods on an instance of `Message` in order to get or set the message body:

`getBody()`

`setBody(Object exchangeBody)` 

The following Groovy Script reads the message body and enhances it with the string `Body is modified`:

```
import com.sap.gateway.ip.core.customdev.util.Message;
import java.util.HashMap;
def Message processData(Message message) {
       def body = message.getBody();
       message.setBody(body + "Body is modified");
       return message;
}
```

> ### Note:  
> Note that conversion of payload into the following formats is supported:
> 
> -   `String`
> 
> -   `InputStream`
> 
> -   `byte[]`
> 
> 
> To convert the payload into String or InputStream use the following `fullyQualifiedClassName`:
> 
> -   `java.lang.String`
> 
> -   `java.io.InputStream`
> 
> 
> To convert the payload into byte\[\], use the following:
> 
> -   For Groovy Script:
> 
>     `def body = message.getBody((byte[]).class);`
> 
> -   For JavaScript:
> 
>     `var body = message.getBody( java.lang.reflect.Array.newInstance(java.lang.Byte.TYPE,0).getClass());`
> 
> 
> To convert the payload into String \(in JavaScript\):
> 
> `var body = message.getBody( new java.lang.String().getClass() );`
> 
> Depending on the actual Camel message content, the `getBody(<type>)` can still use incorrect encoding.
> 
> Consider the following to avoid encoding issues:
> 
> [Avoiding Encoding Issues](avoiding-encoding-issues-3018480.md)
> 
> [Character Encodings: Background Information](character-encodings-background-information-083c971.md)

> ### Note:  
> When converting parts of the message object like the body or even headers or properties into a string \(as `string`\) or into a byte array \(as `byte[]`\) consider that copies of the existing data are created that require extra memory. This resource consumption can even exceed the memory size of the original object if string conversion is executed.
> 
> **Example**:
> 
> `def body = message.getBody(java.lang.String);`
> 
> Depending on the size of the object `byte[]` or string conversion can endanger the worker node with OOM failure. Please consciously decide which part of the message object should be converted.



</td>
</tr>
<tr>
<td valign="top">

Get size of the message body

</td>
<td valign="top">

The following Groovy Script provides the size of the message in bytes, and stores the value as an exchange property \(`bodysize`\):

```
def Message processData(Message message) {
def value = message.getBodySize()
message.setProperty("bodysize", value)
return message;
}
```



</td>
</tr>
</table>

If no Script function is specified in the Script step, the `processData` function is called by default.

