<!-- loiob43d826a8b1441ae871b88787b1cd091 -->

# Enable Streaming of Requests and Responses in an API Proxy

Configure an API proxy to enable HTTP request and response streaming.



## Context

By default, SAP Integration Suite disables streaming of request and response payloads. The payloads are stored directly into a buffer before API proxy pipeline picks them for processing. With streaming disabled, the policies that operate on the payloads work as expected. You can alter this behavior by enabling streaming. When you have enabled streaming, the API proxy pipeline processes the request and response payloads as-is and streams them without any modifications to the client application and to the target endpoint.

You can enable streaming if your API proxy handles large request and response payloads. In SAP Integration Suite, message payload size is restricted to 10 MB for non-streamed HTTP requests and responses.

> ### Note:  
> If your API requests or returns a large amount of data, you may see the following HTTP error: `{"fault":"{\"detail\":{\"errorcode\":\"protocol.http.TooBigBody\"},\"faultstring\":\"Body buffer overflow\"}"}`
> 
> If you encounter this error, we recommend enabling streaming. If the error persists after enabling streaming, consider removing any policies that require access to the request or response payloads.
> 
> When you have enabled streaming, we recommend that you don't attach policies that require access to the request and response payloads. These policies can cause errors or initiate buffering, which limits the payload size and hence defeats the purpose of enabling streaming for handling large payloads. You can attach policies such as Authentication or message logging policies since these policies don't interact with the request and response payloads.



## Procedure

1.  To enable request streaming, in your API proxy bundle, add the `request.streaming.enabled` property in the proxy endpoint and target endpoint definitions and set it to `true`.

2.  To enable response streaming, in your API proxy bundle, add the `response.streaming.enabled` property in the proxy endpoint and target endpoint definitions and set it to `true`.

    You can locate the proxy endpoint and target endpoint definition files in your API proxy bundle under `APIProxy/APIProxyEndpoint` and `APIProxy/APITargetEndPoint`, respectively.

    The following sample code shows how to enable both request and response streaming in the target endpoint definition:

    > ### Sample Code:  
    > ```
    > <TargetEndPoint>
    >     <name>default</name>
    >     <url>https://www.concursolutions.com/api/v3.0/</url>
    >     <provider_id>NONE</provider_id>
    >     <isDefault>true</isDefault>
    >     <properties>
    >         <property>
    >             <name>request.streaming.enabled</name>
    >             <value>true</value>
    >         </property>
    >         <property>
    >             <name>response.streaming.enabled</name>
    >             <value>true</value>
    >         </property>
    >     </properties>
    > </TargetEndPoint>
    > ```

    The following sample code shows how to enable both request and response streaming in the proxy endpoint definition:

    > ### Sample Code:  
    > ```
    > <ProxyEndPoint default="true">
    >     <name>default</name>
    >     <base_path>/concur/api/v3.0</base_path>
    >     <properties>
    >         <property>
    >             <name>request.streaming.enabled</name>
    >             <value>true</value>
    >         </property>
    >         <property>
    >             <name>response.streaming.enabled</name>
    >             <value>true</value>
    >         </property>
    >     </properties>
    > </ProxyEndPoint>
    > ```

    You can also enable streaming directly from the API portal as follows:

    **Enabling Streaming via API portal**

    1.  In the Integration Suite, navigate to the *Configure* \> *APIs* tab.
    2.  Select the API for which you want to enable streaming.
    3.  Choose *Edit* from the top-right corner of the screen.
    4.  Choose *Proxy EndPoint*.
    5.  Under *Proxy Endpoint Properties*, choose *Add*.
    6.  Enter the name of the properties you want to add. In this case, add the `request.streaming.enabled` and `response.streaming.enabled` properties and set their value to `true`.
    7.  Choose *Target EndPoint*.
    8.  Under *Target EndPoint Properties*, choose *Add*.
    9.  Enter the name of the properties you want to add. In this case, add the `request.streaming.enabled` and `response.streaming.enabled` properties and set their value to `true`.
    10. Save the changes.


