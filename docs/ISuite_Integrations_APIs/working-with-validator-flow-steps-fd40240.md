<!-- loiofd402403fb92418692487c8997996f30 -->

# Working with Validator Flow Steps

Validator steps enable you to validate the structure and content of messages processed by an API artifact. You can add these steps to the policy model of your API artifact to ensure that incoming or outgoing messages conform to the expected format before further processing.



## Use

You use validator steps in an API artifact to:

-   Verify that message payloads conform to a defined schema or standard.
-   Detect and handle malformed or invalid messages early in the API flow.
-   Ensure data integrity and compliance with business or industry standards \(for example, EDI or XML\).



## Validator steps


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

EDI Validator

</td>
<td valign="top">

Validates the message payload in EDI flat file format against the configured XSD schema.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define EDI Validator](define-edi-validator-9bf3b96.md).

</td>
</tr>
<tr>
<td valign="top">

XML Validator

</td>
<td valign="top">

Validates the message payload in XML format against the configured XML schema.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Validating Message Payload against XML Schema](validating-message-payload-against-xml-schema-360dc70.md).

</td>
</tr>
</table>

