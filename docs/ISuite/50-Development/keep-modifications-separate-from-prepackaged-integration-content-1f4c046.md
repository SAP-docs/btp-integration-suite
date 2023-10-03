<!-- loio1f4c0465a5524b00906ee49ff3de10ad -->

# Keep Modifications Separate from Prepackaged Integration Content

To avoid overwriting changes, keep the modifications required for the business process separate from the prepackaged integration content provided by SAP.

To support this pattern, you can specify requirements in one or more dedicated custom integration flows, without touching any integration flows from the standard content. Both the standard and the custom integration flows are deployed on the same tenant and are processed in conjunction, communicating with each other using the ProcessDirect adapter. Using the described extension concepts, the customer can keep the standard integration content unchanged. The customer specifies any required enhancements \(for example, specific mappings\) in one or more custom integration flows separate from the standard integration flow.

The basic concept is that a standard integration flow \(predefined by SAP or an SAP partner as part of a standard integration package\) contains one or more customer exits. Through the customer exits, one or more customer integration flows are called. Note that the customer integration flows are designed by the customer who is extending the standard content. The standard integration flow and the custom integration flows \(called through the customer exit\) have to be deployed on the same tenant.

**Related Information**  


[Integration Flow Extension](integration-flow-extension-d374172.md "SAP Integration Suite allows you to extend the capabilities of standard integration content provided by SAP. This approach allows you to implement specific integration scenarios relevant to your business use case without changing the content provided by SAP.")

