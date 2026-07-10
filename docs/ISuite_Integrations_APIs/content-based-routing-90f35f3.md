<!-- loio90f35f3d4fa740a28c49ab2b85940609 -->

# Content-Based Routing

Let's assume that you've an order process where the order can be handled by a specific inventory system depending on the shipping address. Content-based routing forwards the message to the right recipient, depending on the content of a message.



<a name="loio90f35f3d4fa740a28c49ab2b85940609__section_lsp_pzg_sjb"/>

## Implementation

For each receiver branch, you maintain a condition in the form of an XPath expression. The XPath expression can be either based on the payload data or the message header. During message processing, Cloud Integration evaluates the condition, and if met, routes the message to the respective receiver. If no receiver can be determined, Cloud Integration can proceed according to the following variants:

-   Send message to a default receiver.

-   Ignore message.

-   Raise an error.


**Related Information**  


[Variant: Send to Default Receiver](variant-send-to-default-receiver-7ba1864.md "")

[Variant: Ignore](variant-ignore-4998bd8.md "")

[Variant: Raise an Error](variant-raise-an-error-b1148e9.md "")

