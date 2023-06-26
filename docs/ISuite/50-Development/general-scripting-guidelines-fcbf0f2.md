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

    -   When accessing credentials via scripts, try to avoid storing them as headers or properties directly, as Cloud Integration features such as tracing can make them visible in clear text.


-   You can implement logging by using Simple Logging Facade for Java \(SLF4J\) API package. Cloud Integration recommends using SLF4J framework over using your own logging frameworks.

-   If you need xml parsers for more complex operations, use XmlSlurper for read-only parsing and XmlParser for parsing and in-place manipulation of XML.

-   In the XmlSlurper, don’t use the `parseText(String)` method, as it requires the allocation of additional memory space, which doesn’t scale well when you work with large payloads. Instead, use the `parse(Object)` method, for example:

    > ### Sample Code:  
    > ```
    > Reader reader = message.getBody(Reader)
    > def rootNode = new XmlSlurper().parse(reader)
    > 
    > ```

-   Avoid generating pretty-printed versions of xml/json documents. Compacted \(or minified\) documents are normally smaller in size as new line characters and indents are removed from the output. For that reason, a compacted version is preferred when transmitting large documents, for example: `<xml><a>123</a></xml>Reader reader = message.getBody(Reader) def rootNode = new XmlSlurper().parse(reader)`.

-   Don’t include declarations like `Reader reader = message.getBody(Reader)"def body = message.getBody(java.lang.String) as String"`. The use of Groovy coercion \(for example, as String\) is redundant here and can be omitted because the return type of `message.getBody(String)` is already a String. It's enough to write `“def body = message.getBody(java.lang.String)”`.

-   Don't use expressions like `"if (text !=null && text.length() > 0)"` as they can be simplified to `"if (text)"` to check if a string isn’t initial.

-   Avoid using binding variables \(for example `“body = ‘123’”`\). Instead, use typed or untyped definitions \(for example `“String body = ‘123’”` or `“def body = ‘123’”`\). Binding variables lead, on the 1 hand, to longer lifetime of variables. The variable stays in memory until the integration flow is undeployed or redeployed, which can cause *OutOfMemoryError* if large message bodies are processed. On the other hand, however, the binding variables are shared between script executions, which can impact message processing and which are hard to track down. Note that the binding variables aren't thread-safe.

-   Always include explanatory comments in the code.

-   When adding logs in the script, use a switcher that allows to activate or deactivate them. Use the log level of the integration flow or the externalized parameters as switcher.

-   Don't use string objects for string literals that are frequently changed. This causes performance issues as several string objects are created in memory that are consecutively concatenated. This can cause problems when processing large payloads, for example:

    > ### Sample Code:  
    > ```
    > def text = ''
    > 10.times { text += "Line ${it}\r\n" }
    > println(text)
    > 
    > ```

    Instead, use the corresponding StringBuilder and StringBuffer classes, which help to avoid the creation of multiple intermediate string objects, for example:

    > ### Sample Code:  
    > ```
    > StringBuilder sb = new StringBuilder()
    > 10.times { sb.append("Line ${it}\r\n") }
    > def text = sb.toString()
    > 
    > ```

    This pattern can be applied, for example, when you construct the output message payload iteratively and compose it from smaller pieces put together.

-   Don't use the script editor in the Cloud Integration *Design* section, if the code isn’t a simple transformation. Use other external tools \(like IntelliJ IDEA, for example\), which enhance the developer experience.

-   Don't deploy and run the integration flows to test scripts. Instead, use a simulation tool or other external tools \(such as InteliJ IDEA, for example\) to boost productivity.

-   Don‘t use classes generated by `Eval()`.

    Classes generated by `Eval()` are never unloaded. This can cause out of memory situations.

    See: [3246624](https://launchpad.support.sap.com/#/notes/3246624) 


