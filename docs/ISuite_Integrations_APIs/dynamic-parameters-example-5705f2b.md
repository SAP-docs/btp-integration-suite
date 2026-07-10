<!-- loio5705f2b41cca422e967511e3deb1beb4 -->

# Dynamic Parameters \(Example\)

You can define placeholders for parameters of certain adapters or step types. The values of these parameters will then dynamically be set based on the content of the processed message.

For example, parameters *From*, *To*, *Cc*, *Bcc*, *Subject*, *Mail Body* as well as the attachment name, can be dynamically set at runtime from message headers or content.

To set an attribute to be dynamically filled by a message header attribute, enter a variable in the form `${header.attr}` in the corresponding field for the attribute of the corresponding step or adapter.

At runtime, the value of the header attribute \(`attr`\) of the processed message is written into the field for the corresponding attribute of the outbound email.



## Example: Dynamic Attributes for the Mail Adapter

For example, assume that you dynamically define the email *Subject* of the mail adapter as shown in the figure below by the variable `{header.attr}`.

At runtime, a message is received whose header contains a header attribute `attr` with the value `value1`. The mail adapter will then dynamically set the subject of the outbound email with the entry `value1`.

Note that the mail adapter processes message content either already contained in the inbound mail \(from a sender system\) or as modified by content modifier steps on its way between sender and mail adapter.

![](images/Dynamic_Parameters_177bb4e.png)

As shown in the figure, we assume that the inbound message contains a header `header1` with value `value1`. Let us assume that you like to define the *Subject* attribute of the mail receiver adapter dynamically via this header. To do that, specify the *Subject* field by the following entry:

`${header.header1}`

As a result, the mail adapter dynamically writes value `value1` of header `header1` \(from inbound message\) into the subject of the outbound email.

**Related Information**  


[Parameters That Support Dynamic Configuration](parameters-that-support-dynamic-configuration-c9bba0e.md "")

