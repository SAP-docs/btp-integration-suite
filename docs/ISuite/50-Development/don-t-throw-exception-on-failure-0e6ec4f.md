<!-- loio0e6ec4f9f1394f3c9156dcb0d8a25336 -->

# Don't Throw Exception on Failure

Handle an error raised in a receiver system.

Let's assume an integration flow calls a receiver system using the HTTP receiver adapter.

The HTTP receiver adapter comes with a parameter *Throw Exception on Failure*. By default, this option is enabled. This means that Cloud Integration throws an exception on receiving failed HTTP requests. If there's failed HTTP request, the receiver sends a response with an error code \(for example, an HTTP 400 error code\), and, furthermore, message processing fails too. To receive the exception and yet continue with the message processing of the integration scenario, you can disable the option.

This example scenario shows how to handle exceptions raised by a receiver with the *Throw Exception on Failure* option disabled.

Integration flow *Handle Errors - Do Not Throw Error on Failure* calls a receiver. It is designed in the following way.

![](images/Do_Not_Throw_Exception_on_Failure_1_ce50824.png)

> ### Note:  
> Like in other example integration flows, the WebShop example application \(see: [WebShop Example Application](webshop-example-application-767d8ef.md)\) is used as data source.
> 
> We consider the following error situation: An integration flow calls the WebShop with a product identifier, but for the given product identifier no product is available. Note that the WebShop application contains a catalog with fictitious products, and each product can be identified by a product identifier.
> 
> However, if for a given product identifier no product is available, the WebShop's API returns **no** error message. Instead of this, it returns an empty message without any `Product` item. In order to simulate a receiver system that throws an error message, we interconnected the additional integration flow *Webshop Wrapper* between integration flow *Handle Errors - Do Not Throw Error on Failure* and the WebShop API.
> 
> If for a dedicated product identifier a message without any `Product` item is returned from the WebShop, integration flow *Webshop Wrapper* generates an error message with a dedicated HTTP response code and sends the message back to integration flow *Handle Errors - Do Not Throw Error on Failure*.

Integration flow *Handle Errors - Do Not Throw Error on Failure* performs the following steps:

1.  The integration flow receives a message from an HTTP client with the following headers:

    ****


    <table>
    <tr>
    <th valign="top">

    Header
    
    </th>
    <th valign="top">

    Usage
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    productIdentifier
    
    </td>
    <td valign="top">
    
    Contains the product identifier.

    To simulate an error situation, you can

    -   Enter for the header a value for which no product is available.

    -   Omit sending this header to Cloud Integration.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    throwExceptionOnFailure
    
    </td>
    <td valign="top">
    
    Defines how the *Throw Exception on Failure* parameter is set in the HTTP receiver adapter.
    
    </td>
    </tr>
    </table>
    
2.  A *Router* step distinguishes the following cases:

    -   Route with condition: `${header.throwExceptionOnFailure} = 'true'`

        The *Request Reply* step *Call WebShop with Raising Error* calls the receiver with parameter *Throw Exception on Failure* enabled.

        If the HTTP client provides a nonvalid product identifier, the receiver raises an exception and integration flow *Handle Errors - Do Not Throw Error on Failure* fails.

    -   Default route:

        The *Request Reply* step *Call WebShop without Raising Error* calls the receiver with parameter *Throw Exception on Failure* disabled.

        > ### Note:  
        > This is the use case we'd like to focus.

        If the HTTP client provides a nonvalid `productIdentifier` header or no `productIdentifier` header at all, the receiver, implemented by integration flow *Webshop Wrapper*, raises an exception. Integration flow *Handle Errors - Do Not Throw Error on Failure* continues. It handles the exception based on the response code received from the receiver.

        Using a subsequent *Router* step, message processing in the error case is designed for the following error codes:

        ****


        <table>
        <tr>
        <th valign="top">

        Route Name
        
        </th>
        <th valign="top">

        Routing Condition
        
        </th>
        <th valign="top">

        Message Processing
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        200 OK
        
        </td>
        <td valign="top">
        
        $\{header.CamelHttpResponseCode\} = '200'
        
        </td>
        <td valign="top">
        
        Message processing ends. The integration flow sends back the product details to the HTTP client.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        400 Bad Request
        
        </td>
        <td valign="top">
        
        $\{header.CamelHttpResponseCode\} = '400'
        
        </td>
        <td valign="top">
        
        The integration flow sends back the following message to the HTTP client:

        `Your request was invalid. Have you missed to specify the header productIdentifier with a product code?`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        404 not found
        
        </td>
        <td valign="top">
        
        $\{header.CamelHttpResponseCode\} = '404'
        
        </td>
        <td valign="top">
        
        The integration flow sends back the following message to the HTTP client:

        `The item you were looking for does not exist in the web shop`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        other
        
        </td>
        <td valign="top">
        
        \(default route\)
        
        </td>
        <td valign="top">
        
        The integration flow finishes message processing with an error end event.
        
        </td>
        </tr>
        </table>
        


To test the integration scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See:

    [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

    [Setting Up Inbound HTTP Connections (with Basic Authentication), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/391c45cfcd0f4435952ab085283b7f7d.html "") :arrow_upper_right:

2.  Deploy a *User Credentials* artifact with alias name `myCredential` using the *Monitor* application \(*Security Material* tile under *Manage Security*\).

3.  Deploy integration flow *Handle Errors - Do Not Throw Error on Failure* and configure it in such a way that the *User Credentials* parameter fits to the name `myCredential` of the *User Credentials* artifact deployed in the previous step.

4.  Deploy integration flow *Webshop Wrapper*.

5.  In the Postman client, open the *ThrowExceptionOnFailure* folder in the *HandleErrors* collection.

    The following requests are available:

    ****


    <table>
    <tr>
    <th valign="top">

    Request
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    no error, correct identifier
    
    </td>
    <td valign="top">
    
    Request contains a valid product identifier \(`HT-1000`\). Furthermore, header `throwExceptionOnFailure` is set to `false`. This means that the HTTP receiver adapter with parameter *Throw Exception on Failure* disabled is used.

    As response you can expect a message with product details for the given product identifier.

    The integration flow is ended with status *Completed*:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    no error, wrong identifier
    
    </td>
    <td valign="top">
    
    Request contains a nonvalid product identifier \(`HT-10001`\). Furthermore, header `throwExceptionOnFailure` is set to `false`. This means that the HTTP receiver adapter with parameter *Throw Exception on Failure* disabled is used.

    As response you can expect a message with response code `404` and the message content:

    `The item you were looking for does not exist in the web shop`

    The integration flow is ended with status *Completed*:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    no error, missing identifier
    
    </td>
    <td valign="top">
    
    Request doesn't contain any product identifier header. Header `throwExceptionOnFailure` is set to `false`. This means that the HTTP receiver adapter with parameter *Throw Exception on Failure* disabled is used.

    As response you can expect a message with response code `400` and the message content:

    `Your request was invalid. Have you missed to specify the header productIdentifier with a product code?`

    The integration flow is ended with status *Completed*:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    error on Failure, wrong identifier
    
    </td>
    <td valign="top">
    
    Request contains a nonvalid product identifier \(`HT-10001`\). Furthermore, header `throwExceptionOnFailure` is set to `true`. This means that the HTTP receiver adapter with parameter *Throw Exception on Failure* enabled is used.

    You can expect that the integration flow is ended with status *Failed*:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    error on Failure, missing identifier
    
    </td>
    <td valign="top">
    
    Request doesn't contain any product identifier header. Header `throwExceptionOnFailure` is set to `true`. This means that the HTTP receiver adapter with parameter *Throw Exception on Failure* enabled is used.

    You can expect that the integration flow is ended with status *Failed*:
    
    </td>
    </tr>
    </table>
    

> ### Note:  
> You can access the user interface of the WebShop application at the following address to check out valid product identifiers:
> 
> [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html)

**Related Information**  


[HTTP Receiver Adapter](http-receiver-adapter-2da452e.md "Use the HTTP receiver adapter to communicate with target systems using HTTP message protocol.")

