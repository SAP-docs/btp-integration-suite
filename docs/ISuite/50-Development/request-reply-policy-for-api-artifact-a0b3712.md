<!-- loioa0b3712b550a466d859bf9dd0532cc1a -->

# Request Reply Policy for API Artifact

You can use this policy to call an external receiver system in a synchronous step and get back a response.

In certain integration scenarios, the API artifact may need to communicate with an external service, retrieve data from it, and then further process that data. In such cases, you can use the request-reply policy as an exit point to connect to the external service.

In the policy model, you design the external service as a receiver shape and connect the request reply policy with the receiver shape with a receiver channel.

By default, only one request reply policy is created when you create an API artifact. This initial request reply policy cannot be deleted.

Here's an example on how it works:

-   The client sends a request to the HTTP endpoint with the necessary parameters.
-   The target endpoint receives the request, performs the necessary operations \(e.g., database query\), and sends the response back.
-   The client receives the response and processes the data accordingly \(e.g., displays user details\).

