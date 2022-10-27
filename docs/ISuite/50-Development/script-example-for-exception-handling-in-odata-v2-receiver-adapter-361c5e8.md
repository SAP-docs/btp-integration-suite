<!-- loio361c5e87ffff45aea5b23c67c8e02189 -->

# Script Example for Exception Handling in OData V2 Receiver Adapter

You can use the Script step to identify exceptions that arise when sending messages using the OData V2 receiver adapter.

This Groovy Script example performs the following tasks:

-   Saves the value of HTTP response as a message attachment

-   Copies the value of the HTTP error to property `http.ResponseBody`
-   Copies the value of the HTTP error to the message body
-   Copies the HTTP error text and error code to exchange properties

> ### Sample Code:  
> ```
> 
> import com.sap.gateway.ip.core.customdev.util.Message;
> import java.util.HashMap;
> def Message processData(Message message) {
>     // get a map of properties
>     def map = message.getProperties();
>                 
>     // get an exception java class instance
>     def ex = map.get("CamelExceptionCaught");
>     if (ex!=null) {
>                                 
>         // an odata v2 adapter throws an instance of com.sap.gateway.core.ip.component.odata.exception.OsciException
>         if (ex.getClass().getCanonicalName().equals("com.sap.gateway.core.ip.component.odata.exception.OsciException")) {
>                                                 
>             // save the http error request uri as a message attachment 
>             def messageLog = messageLogFactory.getMessageLog(message);
>             messageLog.addAttachmentAsString("http.requestUri", ex.getRequestUri(), "text/plain");
>             // copy the http error request uri to an exchange property
>             message.setProperty("http.requestUri",ex.getRequestUri());
>             
>             // copy the http error response body as an attachment 
>             messageLog.addAttachmentAsString("http.response", message.getBody(), "text/plain");
>             // copy the http error response body as a propert 
>             message.setProperty("http.response", message.getBody());
>             
>             // copy the http error response body as an attachment 
>             messageLog.addAttachmentAsString("http.statusCode", message.getHeaders().get("CamelHttpResponseCode").toString(), "text/plain");
>             
>              // copy the http error response body as a property 
>             message.setProperty("http.statusCode", message.getHeaders().get("CamelHttpResponseCode").toString());
> 
>         }
>     }
> 
>     return message;
> }
> ```

> ### Note:  
> Make sure to call the Script step in an exception subprocess.

