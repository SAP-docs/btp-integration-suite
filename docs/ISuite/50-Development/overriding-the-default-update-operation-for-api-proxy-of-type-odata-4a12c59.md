<!-- loio4a12c5921c8d4358a54548fc90de5ebf -->

# Overriding the Default Update Operation for API Proxy of Type OData

When discovering an API via OData API provider, the update operation is generated automatically based on the backend OData version.

For OData V2 backend service, Integration Suite generates PUT operation as the default update operation. For OData V4 backend service, Integration Suite generates PATCH operation as the default update operation. However, you can override this by adding the key through the API designer for swagger 2.0 or Open API 3.0:

> ### Sample Code:  
> ```
> YAML Format:
> :
> x-sap-default-update-operation: put
> x-sap-default-update-operation: patch
> 
> JSON Format:
> "x-sap-default-update-operation": "put"
> "x-sap-default-update-operation": "patch"     
> 
> ```

In case both the update operations are required, you can pass both the operations as an array as shown below:

> ### Sample Code:  
> ```
> JSON Format:
> "x-sap-default-update-operation": ["put", "patch"]
> 
> YAML Format
> x-sap-default-update-operation:
>     - put
>     - patch
> 
> ```

> ### Note:  
> Use array if only both the operations are required. You can use the API designer to add this key in the Open API specification under “info”. ![](images/Update_Key_c5760ed.png)

Once you have made the changes in the Open API specification, ensure that you *Synchronize* the API proxy for the changes to reflect on the Resource operations.

**Related Information**  


[Create an API Proxy](create-an-api-proxy-c0842d5.md "This topic describes the steps to create an API proxy from the Integration Suite.")

