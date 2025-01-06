<!-- loio35f357c811f546c5ae3451df42f61ea0 -->

# Additional Attributes in OpenAPI Specification

OpenAPI Specification allows you to define additional attributes or custom extensions that start with `x-`, such as `x-sap-api-type`.

You can use an OpenAPI Specification to describe extra functionality of the API that is not covered by the standard OpenAPI Specification.

To know more about these additional attributes, see:

-   [Defined Specification Extensions for OpenAPI Specification v2.0](https://github.com/SAP/openapi-specification/tree/main/sap-schemas/v2.0#defined-specification-extensions)
-   [Defined Specification Extensions for OpenAPI Specification v3.0](https://github.com/SAP/openapi-specification/tree/main/sap-schemas/v3.0#defined-specification-extensions)

To support Application Interface Framework tagging in SAP Business Accelerator Hub, the Open API definition must have the following attributes in the `x-sap-ext-overview` property:

-   Application Interface Framework - Deployment Scenario
-   Application Interface Framework - Namespace
-   Application Interface Framework - Interface Name
-   Application Interface Framework - Interface Version
-   Application Interface Framework - Interface Display Name
-   Application Interface Framework - Recipient Name

You can view a sample here:

> ### Sample Code:  
> ```
> {
>     "x-sap-ext-overview": [
>         {
>             "name": "Application Interface Framework - Deployment Scenario",
>             "values": [
>                 {
>                     "text": "SAP_COM_0287",
>                     "format": "plain"
>                 }
>             ]
>         },
>         {
>             "name": "Application Interface Framework - Namespace",
>             "values": [
>                 {
>                     "text": "/SDLS",
>                     "format": "plain"
>                 }
>             ]
>         },
>         {
>             "name": "Application Interface Framework - Interface Name",
>             "values": [
>                 {
>                     "text": "SO_REPL_O",
>                     "format": "plain"
>                 }
>             ]
>         },
>         {
>             "name": "Application Interface Framework - Interface Version",
>             "values": [
>                 {
>                     "text": "1",
>                     "format": "plain"
>                 }
>             ]
>         },
>         {
>             "name": "Application Interface Framework - Interface Display Name",
>             "values": [
>                 {
>                     "text": "Sales Order Replication",
>                     "format": "plain"
>                 }
>             ]
>         },
>         {
>             "name": "Application Interface Framework - Recipient Name",
>             "values": [
>                 {
>                     "text": "SDLS_SO_REP_OUT_RECIPIENT",
>                     "format": "plain"
>                 }
>             ]
>         }
>     ]
> }
> 
> 
> ```

