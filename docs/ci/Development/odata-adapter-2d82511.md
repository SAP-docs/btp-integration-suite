<!-- loio2d8251111ea74dbbb9f5525db5d9ad04 -->

# OData Adapter

The OData adapter allows you to communicate with an OData API using OData protocol. You use messages in ATOM or JSON format for communication. This OData adapter uses *OData V2* message protocol.

More information: [Configure the OData Sender Adapter](configure-the-odata-sender-adapter-de7aee5.md).

OData adapters only support synchronous communication. In other words, every request must have a response.

> ### Tip:  
> If your input payload contains nodes without data, the output also contains empty strings. If you want to avoid empty strings in the output, ensure that the input payload does not contain any empty nodes.

**Related Information**  


[Configure the OData Sender Adapter](configure-the-odata-sender-adapter-de7aee5.md "")

[Configure the OData V2 Receiver Adapter](configure-the-odata-v2-receiver-adapter-c5c2e38.md "Configure the OData receiver adapter by understanding the adapter parameters.")

[Configure the OData V4 Receiver Adapter](configure-the-odata-v4-receiver-adapter-cd66a12.md "You configure the ODataV4 receiver adapter by understanding the adapter parameters.")

