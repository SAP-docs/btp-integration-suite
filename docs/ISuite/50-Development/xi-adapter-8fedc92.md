<!-- loio8fedc92071b44d2a94402304e1f9e58c -->

# XI Adapter

The XI adapter connects an SAP Cloud Integration tenant to a remote system that can process the XI message protocol.

The XI sender adapter allows you to connect a tenant to a local Integration Engine in a sender system. And the XI receiver adapter allows you to connect it to a sender system. The adapter supports communication over the XI 3.0 protocol.



<a name="loio8fedc92071b44d2a94402304e1f9e58c__section_b2r_xlc_fhc"/>

## Dynamic Headers

The XI sender and receiver adapters handle dynamic headers within XI messages. The `DynamicConfiguration` tag is converted from the incoming message into exchange properties in the XI sender adapter which can be accessed in the integration flow. Each record from this tag has two exchange properties with the `SapDynamicConfiguration` prefix as seen in following table:

****


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

`SapDynamicConfiguration_<Name of the Record>`

</td>
<td valign="top">

Value of the record

</td>
</tr>
<tr>
<td valign="top">

`SapDynamicConfiguration_<Name of the Record>_Namespace`

</td>
<td valign="top">

Namespace of the record

</td>
</tr>
</table>

You can read or modify these properties via content modifier or script.

The receiver adapter checks for these properties and adds them as records within the `DynamicConfiguration` tag for the outgoing message.



<a name="loio8fedc92071b44d2a94402304e1f9e58c__section_mrj_jck_hhc"/>

## Manifest Processing

The XI sender and receiver adapters handle the manifest part of XI messages, which is forwarded in a Camel message and made accessible in the integration flow. The `Manifest` tag is converted from the incoming message into the `SAP_XiManifest` exchange property in the XI sender adapter. The receiver adapter checks for this property and adds it to the `Manifest` tag of the outgoing message.

**Related Information**  


[Configure the XI Sender Adapter](configure-the-xi-sender-adapter-41a1a57.md "The XI sender adapter allows you to connect a tenant to a local Integration Engine in a sender system.")

[Configure the XI Receiver Adapter](configure-the-xi-receiver-adapter-5d2670f.md "The XI receiver adapter allows you to connect a tenant to a local Integration Engine in a receiver system. The adapter supports communication over the XI 3.0 protocol.")

