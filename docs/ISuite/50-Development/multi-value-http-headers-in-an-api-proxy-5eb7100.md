<!-- loio5eb7100e07704de088c5ad4a0a3f7b61 -->

# Multi-value HTTP Headers in an API Proxy

Access and extract multiple values in an HTTP header.

An HTTP header is a name value pair that allows a client application or a backend system to pass additional information about requests and responses. Following are a few examples of simple http headers:

-   `Retry-After: Wed, 05 May 2020 23:59:59 GMT`

    The `Retry-After` request header passes the information about how long the service is unavailable to the requesting client.

-   `Server: APIM/3.0`

    The `Server` header passes the information about the software used by the origin server to handle the request.


An HTTP header can have multiple values depending on <header definition list link\>. A multi-valued HTTP header has comma-separated values. Following are a few examples of headers that contain multiple values:

-   `Content-Language: en, de, fr`
-   `Content-Type: application/json, application/xml, text/html`
-   `Cache-Control: no-transform, no-store, proxy-revalidate`
-   `Accept: text/*, text/html, text/html;level=1, */*`

API Management allows developers to access HTTP headers in policies or in conditional flows using flow variables. Following are a list of variables in API Management that you can use to access a specific HTTP request or response header:

-   `request.header.{header_name}`
-   `request.header.{header_name}.values`
-   `request.header.{header_name}.values.count`
-   `request.headers.count`
-   `response.header.{header_name}`
-   `response.header.{header_name}.values`
-   `response.header.{header_name}.values.count`
-   `response.headers.count`

Following is a sample AssignMessage policy that shows how to read the value of a request header and store it in a variable:

> ### Sample Code:  
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>var</Name>
>     <Ref>request.header.temp</Ref>
>   </AssignVariable
> </AssignMessage>
> 
> ```



<a name="loio5eb7100e07704de088c5ad4a0a3f7b61__section_qrx_t1d_rlb"/>

## Accessing Multiple Values in an HTTP Header

Accessing the values of HTTP headers in API Management policies wherein only the first value of the header is returned is incorrect. The approach of extracting only one value of an HTTP header can lead to issues if the specific header has more than one value. Following are a few examples of multi-value header access:

-   **Example 1**: Read a multi-valued header using javascript code

    Consider that the `Accept` header has multiple values as shown below:

    `Accept: application/xml, text/html, application/xhtml+xml`

    Following is sample JavaScript code that reads the value of Accept header:

    > ### Sample Code:  
    > ```
    > var valuesofacceptheader = context.getVariable(“request.header.Accept”);
    > ```

    The above sample code returns only the first value of the `Accpet` header, which is `application/xml`.

-   **Example 2**: Read a multi-valued header in Assign Message Policy

    Consider that the Access-Control-Allow-Headers header has multiple values as shown below:

    `Access-Control-Allow-Headers: content-type, authorization`

    Following is the sample Assign message policy payload that sets the value of Access-Control-Allow-Headers header:

    > ### Sample Code:  
    > ```
    > <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
    >   <Headers>
    >     <Header name="Access-Control-Allow-Headers">{request.header.Access-Control-Allow-Headers}</Header>
    >   </Headers>
    >   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
    >   <AssignTo createNew="true" transport="http" type="response"/>
    > </AssignMessage>
    > 
    > ```

    The above sample code sets the `Access-Control-Allow-Headers` header with only the first value, which is `content-type`.

    In both the examples above, only the first value of the multi-valued headers are returned. Later, if any other policy in an API proxy tries to use these values to perform some function, then it could lead to errors.




<a name="loio5eb7100e07704de088c5ad4a0a3f7b61__section_lgz_hhd_rlb"/>

## Extracting Multiple Values in an HTTP Header

To extract multiple values in an HTTP header, you can use the relevant built-in flow variables such as `request.header.{header_name}.values.count`, `request.header.{header_name}.values`, `response.header.{header_name}.values.count`, and `response.header.{header_name}.values`.

You can then iterate to retrieve all the values from a specific header using a sample JavaScript code as shown below:

> ### Sample Code:  
> ```
> for (var i = 1; i <=context.getVariable('request.header.Content-Type.values.count'); i++)
> {
>   print(context.getVariable('request.header.Content-Type' + i));
> }
> ```

