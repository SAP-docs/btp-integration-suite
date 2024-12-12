<!-- loiofcbf0f20059a4ffba7dfda7d28830ccd -->

# General Scripting Guidelines



Follow these general guidelines when using the *Script* step.

-   Consider these following general recommendations:

    -   Use standard integration flow steps wherever possible, such as the splitting of messages, or encoding, etc.

    -   SAP does only furnish a guarantee for the officially supported script APIs \(see [Define a Local Script Step](define-a-local-script-step-03b32eb.md)\).

    -   When you use custom scripts, you need to maintain them by yourself. SAP doesn't furnish any guarantee that after Cloud Integration upgrades custom scripts still work as expected.


-   Don't use scripts as a substitute for steps that are already provided as standard out-of-the-box integration flow steps, such as the splitting of messages, or encoding, etc.

    -   If possible, avoid using xml and json parsers for xml or json transformations. Instead, use the easier, more readable, and more maintainable option: standard mappings and XPath expressions in content modifiers.

    -   Don't access credentials to write them into http headers. Instead, use standard channels with User Credential Artifacts.


-   Avoid exposing sensitive information in scripts.
    -   When accessing credentials via scripts, try to avoid storing them as headers or properties directly, as Cloud Integration features such as tracing can make them visible in clear text.

    -   When using the *Optimize* feature, ensure that the source code of Groovy scripts doesn't contain any sensitive information. For more details, see [3542713](https://me.sap.com/notes/3542713).

-   Direct usage of Open Source classes isn't supported.

    Scripts that use direct open source classes may not work with the upcoming open source software versions because of incompatible changes in the open source libraries. Use Cloud Integration's Script APIs or native Groovy classes to ensure compatibility during the open source updates.

    Script APIs are stable and independent of updates to open source libraries. See: [SDK API](sdk-api-c5c7933.md) and [Using Script API Methods in Groovy Scripts](using-script-api-methods-in-groovy-scripts-062f7a7.md).

-   You can implement logging by using Simple Logging Facade for Java \(SLF4J\) API package. Cloud Integration recommends using SLF4J framework over using your own logging frameworks.

-   If you need xml parsers for more complex operations, use XmlSlurper for read-only parsing and XmlParser for parsing and in-place manipulation of XML.

-   In the XmlSlurper, don’t use the `parseText(String)` method, as it requires the allocation of additional memory space, which doesn’t scale well when you work with large payloads. Instead, use the `parse(Object)` method, for example:

    > ### Sample Code:  
    > ```
    > Reader reader = message.getBody(Reader)def rootNode = new XmlSlurper().parse(reader)
    > ```

-   Avoid generating pretty-printed versions of xml/json documents. Compacted \(or minified\) documents are normally smaller in size as new line characters and indents are removed from the output. For that reason, a compacted version is preferred when transmitting large documents, for example: `<xml><a>123</a></xml>`.

-   Don’t include declarations like `"def body = message.getBody(java.lang.String) as String"`. The use of Groovy coercion \(for example, as String\) is redundant here and can be omitted because the return type of `message.getBody(String)` is already a String. It's enough to write `“def body = message.getBody(java.lang.String)”`.

-   Don't use expressions like `"if (text !=null && text.length() > 0)"` as they can be simplified to `"if (text)"` to check if a string isn’t initial.

-   Avoid using binding variables \(for example `“body = ‘123’”`\). Instead, use typed or untyped definitions \(for example `“String body = ‘123’”` or `“def body = ‘123’”`\). Binding variables lead, on the 1 hand, to longer lifetime of variables. The variable stays in memory until the integration flow is undeployed or redeployed, which can cause *OutOfMemoryError* if large message bodies are processed. On the other hand, however, the binding variables are shared between script executions, which can impact message processing and which are hard to track down. Note that the binding variables aren't thread-safe.

-   Always include explanatory comments in the code.

-   When adding logs in the script, use a switcher that allows to activate or deactivate them. Use the log level of the integration flow or the externalized parameters as switcher.

    > ### Note:  
    > To read the actual log level at runtime during integration flow processing, you can use a Groovy script. An example script is given at [Setting Log Levels](setting-log-levels-4e6d3fc.md).
    > 
    > If you want to configure a scenario so that a specific log level is set for an integration flow at runtime, follow these steps: Pass the header `SAP_MessageProcessingLogLevel` with the input message and choose the desired log level as the header value. The processing of the integration flow will then be recorded at runtime with the specified log level \(see also [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)\).

-   Don't use string objects for string literals that are frequently changed. This causes performance issues as several string objects are created in memory that are consecutively concatenated. This can cause problems when processing large payloads, for example:

    > ### Sample Code:  
    > ```
    > def text = ''10.times { text += "Line ${it}\r\n" }println(text)
    > ```

    Instead, use the corresponding StringBuilder and StringBuffer classes, which help to avoid the creation of multiple intermediate string objects, for example:

    > ### Sample Code:  
    > ```
    > StringBuilder sb = new StringBuilder()10.times { sb.append("Line ${it}\r\n") }def text = sb.toString()
    > ```

    This pattern can be applied, for example, when you construct the output message payload iteratively and compose it from smaller pieces put together.

    With regards to the differences between StringBuilder and StrinBuffer \(while both are used to create mutable objects that can be further stringified\), StringBuffer's public methods are synchronized, leading to thread safety of StringBuffer objects in a multi-threaded environment; whereas StringBuilder is not thread-safe. Yet, thread safety comes at the cost of performance overhead. As a result, as a user, evaluate and assess if thread safety / synchronization is needed. If so, consider using StringBuffer. If thread safety is not a concern, the performance can be further optimized by using StringBuilder instead.

-   Don't use the script editor in the Cloud Integration *Design* section, if the code isn’t a simple transformation. Use other external tools \(like IntelliJ IDEA, for example\), which enhance the developer experience.

-   Don't deploy and run the integration flows to test scripts. Instead, use a simulation tool or other external tools \(such as InteliJ IDEA, for example\) to boost productivity.

-   Don‘t use classes generated by `Eval()`. Classes generated by `Eval()` are never unloaded. This can cause out of memory situations.

    See: SAP Note [3246624](https://me.sap.com/notes/3246624).

-   Don't use the `TimeZone.setDefault` method. This method changes the default time zone of the virtual machine, which can lead to multiple technical issues, for example, issues with database connectivity.

    To learn what to do instead of using this method, see SAP note [3289679](https://me.sap.com/notes/3289679).

-   Define your script’s import statement so that it consumes native APIs from one of the following APIs:

    -   SDK Groovy API

        See:

        [SDK API](sdk-api-c5c7933.md)

        [Groovy SDK Java doc](https://help.sap.com/doc/a56f52e1a58e4e2bac7f7adbf45b2e26/Cloud/en-US/index.html)

    -   Native Groovy APIs

        See: [Groovy JDK API Documentation](https://groovy-lang.org/gdk.html)

        In particular, all supported APIs up to Groovy runtime version 2.4.21 are supported.

        See also: [Define a Local Script Step](define-a-local-script-step-03b32eb.md)

    -   APIs from the Cloud Integration stack, that means, jar files that are bundled in the Cloud Integration software assembly


    We don’t recommend to consume external code \(uploaded as integration flow resource\). If you do so, a warning is raised.

-   Use CodeNarc to analyze your Groovy code for defects, bad practices, inconsistencies, and style issues, for example \(static check\).

    Supported CodeNarc version: 3.4.0

    See: [CodeNarc](https://github.com/CodeNarc/CodeNarc)


