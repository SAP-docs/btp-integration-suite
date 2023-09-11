<!-- loio6891f9e11cd344ddb6455790aa6e4a21 -->

# Using Additional Filter Criteria

You can filter message processing logs using additional filter criteria.

The following additional filter criteria are available \(depending on the integration flow design\):

-   *Sender*

    Identifier set by a dedicated header \(`SAP_Sender`\).

-   *Receiver*

    Identifier set by a dedicated header \(`SAP_Receiver`\).

-   *Custom Status*

    Identifier set by a dedicated exchange property \(`SAP_MessageProcessingLogCustomStatus`\).

-   *Application Message Type*

    Identifier set by a dedicated header \(`SAP_MessageType`\).

-   *Custom Header*

    Filter for a dedicated value of a custom header by entering an expression like:

    <custom header name\> = <custom header value\>

    For more information on how to set up a custom header, check out [Use Custom Header Properties to Search for Message Processing Logs](https://help.sap.com/docs/integration-suite/sap-integration-suite/use-custom-header-properties-to-search-for-message-processing-logs).

    You can also get custom header properties using an OData V2 application programming interface \(API\). See: [Get Custom Header Properties](https://help.sap.com/docs/integration-suite/sap-integration-suite/get-custom-header-properties).


A value help is available for the *Sender*, *Receiver*, *Custom Status*, and *Application Message Type* fields. The list of available values depends on your integration design.

To filter for a dedicated value of a custom header, in the *Custom Header* field, enter an expression like: `<custom header name> = <custom header value>`

Alternatively, you can search for IDs in the*ID* field, and display messages associated with various IDs such as:

