<!-- loio46868626fdfd478d8183a4246fda4ea6 -->

# Remove Sensitive or Secret Content Before Logging or Forwarding

Make sure that no sensitive or secret data is written into the message processing log and that no such data is sent to an external system, unless it's needed by the business scenario.



<a name="loio46868626fdfd478d8183a4246fda4ea6__section_vyq_z2s_tjb"/>

## Use Case

If you use the message logging mechanism of SAP Integration Suite to write message content into the message log, remove sensitive data \(such as passwords or secret keys\) before logging it.

Everything you write into a message log is visible in message monitoring. Take special care when you log all headers. The list of headers can, for example, contain the authorization header.

Similarly, before sending the message, remove all sensitive headers that are not to be revealed to an external system.



<a name="loio46868626fdfd478d8183a4246fda4ea6__section_gyj_1fs_tjb"/>

## Implementation

To avoid the leaking of unwanted content into the log, you can apply one of the following options:

-   Include all content that you explicitly want to put into the log \(the preferred approach\).

-   Exclude all content that contains sensitive content.


For the removal of unwanted headers in the on-the-wire message, use the Content-Modifier step and delete the respective headers.

Both methods are shown in the reference integration flow.

The *Apply Security - Remove Sensitive Content* integration flow shows how to implement this guideline.

![](images/RemoveSensitiveContent_754b5bd.png)

The Script step contains the following script:

> ### Sample Code:  
> ```
> import com.sap.gateway.ip.core.customdev.util.Message; 
> import java.util.HashMap; 
> def Message processData(Message message) { 
>        def messageLog = messageLogFactory.getMessageLog(message) 
>        // Log Headers  
>        def map = message.getHeaders(); 
>        // Log only needed headers (allow list)  
>        messageLog.setStringProperty("Content-Type (allowlist)",map.get("Content-Type")) 
>        messageLog.setStringProperty("Accept (allowlist)",map.get("Accept")) 
>        // exclude sensitive headers (block list)     
>        map.each{ k, v -> if (!k.equals("authorization"))  messageLog.setStringProperty(k+" (blocklist)", v) } 
>        return message; 
> } 
> ```

It logs some headers into the message processing log. The 1st part logs only the wanted headers \(allow list\) and the 2nd all but the unwanted \(block list\).

The Content Modifier removes the authorization header. To specify this behavior, a constant header with the *Name* attribute specified as `$name=authorization` and the *Action* specified as *Delete* is added.

The same caution also has to be observed in the following cases:

-   The sensitive content is not contained in headers but in properties or the payload.

-   The logging is done via the server log.


If you use standard logging mechanisms such as integration flow tracing, the built-in message processing log, or the persist step, the software makes sure that standard headers that contain secrets like the authorization header are not revealed to any log.

For general considerations on logging from a security point of view, see [https://cheatsheetseries.owasp.org/cheatsheets/Logging\_Cheat\_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html).

