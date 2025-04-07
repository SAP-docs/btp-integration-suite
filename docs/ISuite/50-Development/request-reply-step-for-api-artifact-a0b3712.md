<!-- loioa0b3712b550a466d859bf9dd0532cc1a -->

# Request Reply Step for API Artifact

You can use this step to call an external receiver system in a synchronous step and get back a response.

In certain integration scenarios, the API artifact may need to communicate with an external service, retrieve data from it, and then further process that data. In such cases, you can use the request-reply step as an exit point to connect to the external service.

In the policy model, you design the external service as a receiver shape and connect the request reply step with the receiver shape with a receiver channel.

By default, only one request reply step is created when you create an API artifact. This initial request reply step cannot be deleted.

Here's an example on how it works:

-   The client sends a request to the HTTP endpoint with the necessary parameters.
-   The server processes the request, performs the necessary operations \(e.g., database query\), and constructs a response.
-   The server sends the response back to the client.
-   The client receives the response and processes the data accordingly \(e.g., displays user details\).

> ### Caution:  
> The request reply step does not work with all available adapter types.
> 
> Adapters that can be used with the following receiver adapter types:
> 
> -   HTTP
> 
>     See, [HTTP Receiver Adapter](http-receiver-adapter-2da452e.md)

**Related Information**  


[Adding an API Artifact](adding-an-api-artifact-c2fe62c.md "Add an API artifact to an package.")

[Copying an API Artifact](copying-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API but with some modifications or variations. The copy feature allows you to quickly duplicate the API artifact and make the necessary changes without starting from scratch.You can create a duplicate of an API artifact by copying it within the same package or in a different integration package within the same SAP Integration Suite subscription.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policy steps.")

[Deploying an API Artifact](deploying-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime profile in order to make it executable and ready for use.")

