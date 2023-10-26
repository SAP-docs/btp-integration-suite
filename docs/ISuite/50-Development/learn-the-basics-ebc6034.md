<!-- loioebc6034cd1044e4093683cf61425175a -->

# Learn the Basics

Understand the basic capabilities for modeling integration flows.

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Learn the Basics](https://api.sap.com/package/DesignGuidelinesModelingBasics/integrationflow)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

The integration package contains various integration flows that help you to achieve the following learning targets.


<table>
<tr>
<th valign="top">

Learning Target

</th>
<th valign="top">

Integration Flows

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Get started with integration flow design, starting with a set of 3 simple integration flows showing basic features of message processing \(with increasing complexity\).

</td>
<td valign="top">

*Modeling Basics - Timer-Initiated Scenario*

*Modeling Basics - Timer-Initiated Scenario with External Data Source and Receiver*

*Modeling Basics - Sender-Initiated Scenario with External Data Source and Receiver*

</td>
<td valign="top">

[Getting Started](getting-started-0a80259.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to access \(and set\) headers and properties.

</td>
<td valign="top">

*Modeling Basics - Access Header And Properties In Message Mapping*

*Modeling Basics - Access Header And Properties In XSLT Mapping*

*Modeling Basics - Access Header And Properties In XPATH And Conditions*

</td>
<td valign="top">

[Access Headers and Properties](access-headers-and-properties-4a03fcd.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to design integration scenarios with integration flow-to-integration flow communication.

</td>
<td valign="top">

No predefined integration flows are available for this learning target.

</td>
<td valign="top">

[Communication between Integration Flows](communication-between-integration-flows-ab5db7b.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to configure adapters.

</td>
<td valign="top">

*Modeling Basics - Consume a Public HTTP Service With Query Parameters* \(covers the HTTP receiver adapter\)

</td>
<td valign="top">

[Configure Adapters](configure-adapters-d0a6bc8.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to transport integration content from a source to a target tenant.

</td>
<td valign="top">

You find documentation of the transport options and criteria that help you to decide which option to choose for your integration project.

No predefined integration flows are available for this learning target.

</td>
<td valign="top">

[Content Transport](content-transport-cb7d2f1.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to implement different scenarios to decouple sender and integration flow processing.

</td>
<td valign="top">

*Modeling Basics – Decouple Flows Without Persistence*

*Modeling Basics – Decouple Flows Using Persistence*

*Modeling Basics – Decouple Flows With Polling Consumer*

</td>
<td valign="top">

[Decouple Processing](decouple-processing-3ef92e4.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to retrieve only delta data from the source system using the current date or the latest date in the payload.

</td>
<td valign="top">

*Modeling Basics - DeltaSync Timestamp via Date Now*

*Modeling Basics - Delta Sync With Timestamp Via Payload*

</td>
<td valign="top">

[Delta Synchronization](delta-synchronization-012be7e.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to handle exceptions with an exception subprocess.

</td>
<td valign="top">

*Handle Errors - Extend With Exception Subprocess - End Event*

*Handle Errors - Extend With Exception Subprocess – Error End Event*

*Handle Errors - Extend With Exception Subprocess – Escalation End Event*

> ### Note:  
> These integration flows are part of the integration package [Integration Flow Design Guidelines - Handle Errors Gracefully](https://api.sap.com/package/DesignGuidelinesHandleErrors?section=Overview).



</td>
<td valign="top">

[Handle Exceptions](handle-exceptions-445a0c6.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to use the *Monitor* application to analyze the behavior of an integration flow at runtime.

</td>
<td valign="top">

You find a summary of the monitoring features and guidelines how to use them.

</td>
<td valign="top">

[Message Monitoring](message-monitoring-8398448.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to modify content.

Learn how to use different integration flow steps \(for example, the content modifier or the content enricher\) to modify the message content.

-   Learn how to convert data from a source into a target format.

-   Learn how to encode and decode content.

-   Learn how to handle message mappings.




</td>
<td valign="top">

Convert data:

-   *Modeling Basics - CSV To XML Converter*

-   *Modeling Basics - XML To CSV Converter*

-   *Modeling Basics - JSON to XML Converter And XML to JSON Converter*


Encode/decode content:

-   *Modeling Basics - MIME Multipart Encoder Decoder*

-   *Modeling Basics - Base64 Encoder*

-   *Modeling Basics - Base64 Decoder*


Message mapping:

*Modeling Basics - Mapping Context*

</td>
<td valign="top">

[Modify Content](modify-content-fc0d3c4.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to use steps that store the message on the tenant database.

</td>
<td valign="top">

*Modeling Basics - Use the Persist Step* \(is used together with the *Message Stores* OData API to show how to store and retrieve message store entries\)

*Modeling Basics - Usage Of Data Store*

</td>
<td valign="top">

[Persistence](persistence-0c93d55.md) 

</td>
</tr>
<tr>
<td valign="top">

Learn how to transfer files.

</td>
<td valign="top">

*File Transfer – Poll File by Done File*

*File Transfer – Poll Folder by Fixed Done File*

*File Transfer - Concatenating Files via Poll Enrich*

*File Transfer - Combine XML Files via Poll Enrich*

*File Transfer – Poll and Merge Folder*

</td>
<td valign="top">

[Transfer Files](transfer-files-9bda753.md) 

</td>
</tr>
</table>

