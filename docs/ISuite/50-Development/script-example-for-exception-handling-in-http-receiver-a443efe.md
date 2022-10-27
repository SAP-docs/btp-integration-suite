<!-- loioa443efe1d5d2403fb95ee9def1a672d4 -->

# Script Example for Exception Handling in HTTP Receiver

You can use the Script step to identify exceptions that arise when sending messages using the HTTP receiver adapter.

This Groovy Script example performs the following tasks:

-   Saves the value of HTTP response as a message attachment

-   Copies the value of the HTTP error to property `http.ResponseBody`
-   Copies the value of the HTTP error to the message body
-   Copies the HTTP error text and error code to exchange properties

> ### Sample Code:  
> ```
> import com.sap.gateway.ip.core.customdev.util.Message;
> 
> def Message processData(Message message) {
>                 
>                 // get a map of properties
>                 def map = message.getProperties();
>                 
>                 // get an exception java class instance
>                 def ex = map.get("CamelExceptionCaught");
>                 if (ex!=null) {
>                                 
>                                 // an http adapter throws an instance of org.apache.camel.component.ahc.AhcOperationFailedException
>                                 if (ex.getClass().getCanonicalName().equals("org.apache.camel.component.ahc.AhcOperationFailedException")) {
>                                                 
>                                                 // save the http error response as a message attachment 
>                                                 def messageLog = messageLogFactory.getMessageLog(message);
>                                                 messageLog.addAttachmentAsString("http.ResponseBody", ex.getResponseBody(), "text/plain");
> 
>                                                 // copy the http error response to an exchange property
>                                                 message.setProperty("http.ResponseBody",ex.getResponseBody());
> 
>                                                 // copy the http error response to the message body
>                                                 message.setBody(ex.getResponseBody());
> 
>                                                 // copy the value of http error code (i.e. 500) to a property
>                                                 message.setProperty("http.StatusCode",ex.getStatusCode());
> 
>                                                 // copy the value of http error text (i.e. "Internal Server Error") to a property
>                                                 message.setProperty("http.StatusText",ex.getStatusText());
>                                                 
>                                 }
>                 }
> 
>                 return message;
> }
> ```

> ### Note:  
> Make sure to call the Script step in an exception subprocess.

