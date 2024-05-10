<!-- loio0c1c96e50ff340869090469d260976f3 -->

# Specify the Runtime Configuration

Specify the runtime properties of the integration flow.



## Procedure

1.  Open the integration flow and select the graphical area outside the integration flow model.

2.  Choose the *Runtime Configuration* tab.

3.  Specify the following properties.

    With the property *Runtime Profile*, you choose the target runtime environment for the integration content designed with the application.

    A runtime profile defines a set of capabilities for Cloud integration content design supported by a specific target integration platform. For example, a specific runtime profile supports the configuration of a specific set of adapter types and integration flow steps. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).

    **Runtime Configuration Properties**


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Allows you to ...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Namespace Mapping* 
    
    </td>
    <td valign="top">
    
    Map a prefix to a namespace at runtime.

    Enter a namespace-prefix pair with a format `xmlns:<prefix>=<namespace>`.

    This parameter is required for elements such as the content-based router, content modifier or content filter that can use namespaces in their configuration. You can either enter the namespace-prefix pair or the tool automatically fills the namespace-prefix pair whenever a lookup is performed for the assigned WSDL.

    You can also enter multiple namespace-prefixes as shown in the example: `xmlns:test=http://sapcd.com/testABC;xmlns:test2=http://sapcd.com/testPQR`.

    > ### Note:  
    > `xmlns:ns0=https://hcischemas.netweaver.neo.com/hciflow`
    > 
    > Here, `ns0` is the prefix and `https://hcischemas.netweaver.neo.com/hciflow` is the namespace. That way, in a router, you can specify the routing condition for an XML message as:
    > 
    > ```
    > /ns0:HCIMessage/SenderID='Sender01'
    > ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Message Processing Log* 
    
    </td>
    <td valign="top">
    
    Configure the log level to display in the *Monitoring* editor.

    Select one of the log levels from the *Message Processing Log* dropdown.

    -   *All Events*: Allows all messages to be logged and displayed.
    -   *Error Events*: Allows only error messages to be logged and displayed.
    -   *No Logging*: Hides logging information.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Allowed Header\(s\)* 
    
    </td>
    <td valign="top">
    
    Specify the headers to be retained when the incoming message is processed.

    > ### Caution:  
    > Only include the headers that are truly needed in the further processing of the message. This is the only way to ensure that no headers are processed that may have unwanted side effects or pose a security risk. Entering a wildcard character \(`*`\) bears the risk that you can’t control which headers will be processed by the integration flow.

    > ### Note:  
    > Enter one or more names of headers by separating them with the pipe character \(`|`\). Ensure that the header names separated with the pipe character don't have any whitespaces in between.
    > 
    > As a smart way to specify several headers with similar names, you can use regular expressions \(regex\).
    > 
    > Examples:
    > 
    > -   The expression `ab.` matches `ab` and any three-character string starting with `ab` \(for example: `abc`, `abd`\).
    > 
    > -   The expression `ab?cd` matches `acd` or `abcd`.
    > 
    > -   The expression `AB_[0-9][0-9][0-9][0-9]` matches `AB_` followed by 4 digits, for example, `AB_1234`, `AB_5678`.
    > 
    > -   The expression `AB_[0-9]|CD_[0-9]` matches `AB_` followed by one digit or `CD_` followed by one digit, for example: `AB_1`, `AB_2`, `CD_9`.
    > 
    >     Note that contants separated with the pipe character \(`|`\) \(as mentioned above\) is also a regular expression.
    > 
    >     You can also combine contant values with regular expressions, separated by the pipe character \(`|`\).
    > 
    >     Example: `AB_[0-9]|ABC`
    > 
    > 
    > Additionally to using regex, you can use a single wildcard \(`*`\) to allow all headers.

    In general, headers used by the runtime components are retained and other headers are removed during message processing. This field is useful when you need specific header information along with the message body.

    For inbound SSL connections \(when a sender calls SAP Cloud Integration\), senders have to authenticate against a load balancer component. The load balancer sets the following message header fields: `SSL_CLIENT_CERT` \(contains the Base64-encoded sender client certificate\) and `SSL_CLIENT_USER`. Entering these values in the *Allowed Header\(s\)* field, allows you to forward these headers during message processing.

    > ### Remember:  
    > When you want to use Principal Propagation as the authentication method to connect with an on-premise system, don't pass any authorization headers. Follow the approach recommended by SAP BTP Connectivity. See: [Authentication to the On-Premise System](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/67b0b94f09f2446598787eea0855e56b.html).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *HTTP Session Reuse* 
    
    </td>
    <td valign="top">
    
    Choose one of the following options:

    -   *None*

        Session handling is switched off.

    -   *On Exchange*

        Each exchange corresponds to a single session \(use this option for stateful services\).

    -   *On Integration Flow*

        Only one session will be used across the whole integration flow \(only use this option for stateless services\).

        > ### Note:  
        > Once an HTTP session has been initialized, there is usually no further authentication for the duration of the session \(one of the advantages of using sessions\). This means that all further HTTP requests on that server are processed in the context of the user that was logged on when the session was initialized. If this behavior doesn't meet your requirements \(for example, the user is dynamic and can change from request to request\), you can select either an exchange session scope \(if the user remains the same for at least the processing of a single message\) or no session.

        > ### Note:  
        > SuccessFactors \(OData V4\) and SuccessFactors \(REST\) adapters do not support HTTP session handling.



    
    </td>
    </tr>
    </table>
    
    In the case of OData API artifacts, you can only specify the *Namespace Mapping* property.

4.  Save the changes.


**Related Information**  


[Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md "Integration Suite allows you to design integration content for different target integration platforms. Accordingly, different runtime profiles are available to adapt the user interface of the integration content designer to the specifications and capabilities of the target integration platform.")

[Define Content Modifier](define-content-modifier-8f04a70.md "")

