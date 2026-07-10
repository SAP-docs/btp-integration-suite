<!-- loiodc240745c3d040a5835ae2089a78a192 -->

# Optimize Memory Footprint

During message processing, resources such as CPU, memory, connections, etc., are consumed. In this guideline, we focus on the memory consumption



Examples of data that is kept in memory are, for example, the message payload, script content, exchange properties, or headers that are accessed or written during message processing. Depending on the integration flow step or the chosen technology, memory is allocated to a lesser or larger degree, so for instance, a DOM parser usually allocates more memory than a SAX parser. Furthermore, a bad design of your integration flow that keeps unnecessary data in the main memory can lead to a larger memory footprint. It can happen that your integration scenario needs more memory than what’s available, leading to an out of memory situation that then also impacts other scenarios running on the same tenant.

In the following, we provide guidelines about how to optimize the memory footprint when running your integration scenario.

> ### Note:  
> The following guidelines are to be considered if you handle large data. Usually, if your data isn't extraordinarily large, you may not face memory issues, and hence don't need to apply specific memory optimizing measures.



### Multiple Branches

*Context*: When your flow has multiple branches, e.g., through a multicast, make sure that before you end a branch via join and gather, you empty or reset all the data that isn't required beyond that step.

*Why*: In a Multicast scenario, each branch is duplicating the entire content of the parent branch. Therefore, also the memory consumption rises. Unless you explicitly reset it, the branch data is kept in memory until the integration process ends.

*How*: In a content modifier step, you can clean the headers and properties. Furthermore, you can set the body to a smaller sized value.



### Multicasting with Large Data

*Context*: If you expect large data volumes, avoid multicasting if possible.

*Why*: Multicasting multiplies data and hence stores it multiple times in the memory. Example: Let’s assume you have 2 branches. Then, the payload is stored 3 times in the main memory: once for the original exchange and, in addition, once for each branch.

*How*: If possible, try to do all processing in a single exchange instead. That means, in sequence, by buffering the payload in a property and restoring it once required.



### Variables in Scripts

*Context*: In a script, empty variables that you initiated in the script and which keep large data.

*Why*: If you define variables in a script, the variables are kept in memory even if the processing of the script ended. The memory is kept until the entire integration process ends.

*How*: Remove particular variables from the script.

> ### Tip:  
> To remove a variable, you can use the following method:
> 
> `binding.variables.remove 'varname'` 



### Transformation of Large Payloads

*Context*: Avoid memory-intensive transformation on a large message payload.

*Why*: Risk of running out of memory.

*How*: Instead, try to use splitter wherever possible to break large messages into smaller chunks. If your backend can also process small chunks, consider sending those chunks to the receiver instead of aggregating the chunks back into 1 payload. If nevertheless, the receiver expects the entire request in total, collect the processed data before sending it to the receiver. In this case, check if streaming can be applied.



### Byte compared with String

*Context*: Instead of String, use ByteArray as output types if possible, especially if you process large messages.

*Why*: A Character in String format needs 2 Bytes, whereas a character in Byte format only needs one. Therefore, the memory consumption for Byte is lower than compared to String.

*How*: In an XSLT mapping, for instance, you can select the output type. Unless your next flow expects a String as input \(for example a Script with getBody\(java.lang.String\)\), choose ByteArray. Try to stick to the same format across flow steps in order to avoid expensive transformations. Note that this rule may not be always possible.



### Global Variables and Headers

*Context*: Clean up header when using global variables.

*Why*: Global variables use headers to perform DB operations. Whenever you write a variable on the DB, the value is stored in a temporary header in a preliminary step. But: this header isn't removed after the DB operation and therefore the value is still kept in memory until the end of the integration flow processing.

*How*: If the variable content is large, it's beneficial to remove the header \(having the same name as the global variable\) after the DB operation. This can be done in a content modifier step.



### XPATH Conditions

*Context*: When using XPATHs in your conditions, try to use absolute path as much as possible.

*Why*: Relative XPATH expressions are very memory expensive, especially for large documents, as the parser searches the whole document for the specified element.



### DOM compared with SAX Parsers

*Context*: Consider the parser capabilities and footprint before choosing the parser.

*Why*: DOM parsers are memory intensive as they load the entire XML in memory and create the XML tree from it. This is an important consideration especially when you work with large datasets as they can cause an out-of-memory situation.

*How*: Check if you can use a SAX parser instead. SAX parsers are helpful when working with huge datasets as they stream the XML and don’t load the entire XML in memory. However, if the dataset isn't huge, DOM parsing can prove to be more performant. DOM parsing can also be a better choice when you need to parse the XML back and forth. Moving the XML back and forth with a SAX parser however is expensive.



### Use Streaming in General

*Context*: Use streaming if possible.

*Why*: Processing large messages can lead to high processing times and high memory consumption. In the worst case, it even leads to out of memory issues.

*How*: If you model your integration flow, take flow steps that do support streaming into account. For a complete list of flows steps and their streaming characteristics, see [Optimize Integration Flow Design for Streaming](optimize-integration-flow-design-for-streaming-396941a.md).



### Use Streaming in Scripts

*Context*: Use streaming when accessing an XML message in a script \(if possible\).

*Why*: If you use an XMLSlurper in a Groovy script to process XML messages, depending on the data type of the message body, additional memory may be allocated. If the body is large or if many messages are processed in parallel, the additional memory footprint causes out of memory issues.

*How*: The additional memory footprint can be avoided by streaming the body to the XMLSlurper. See [Stream the XMLSlurper input in Groovy Scripts](https://blogs.sap.com/2017/06/20/stream-the-xmlslurper-input-in-groovy-scripts/)

