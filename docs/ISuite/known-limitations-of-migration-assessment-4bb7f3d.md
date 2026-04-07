<!-- loio4bb7f3d56b14424c85d8acbcebfde2a7 -->

# Known Limitations of Migration Assessment

The following table describes the known limitations of Migration Assessment:

****


<table>
<tr>
<th valign="top">

Components

</th>
<th valign="top">

Limitation

</th>
</tr>
<tr>
<td valign="top">

Service Interface

</td>
<td valign="top">

When the Service Interface \(SI\) used in an Integration Configuration \(ICO\) exists only in the *Integration Directory* \(for example, under a Business Component\) but it doesn't exist in the *Enterprise Services Repository* \(ESR\), Migration Assessment cannot retrieve its metadata. As a result, the following message appears in the assessment report: “Couldn’t find service interface details.”.

This occurs because Migration Assessment depends on the ESR definition of the Service Interface to extract message structure and operation details. If the object exists only in the Directory, Migration Assessment has no access to its ESR metadata and therefore can't analyze the interface structure.

In practice, such cases are often related to “dummy passthrough” or file-to-file scenarios, where no ESR objects are created. For these scenarios, Migration Assessment typically ignores the missing ESR definition, as the interface doesn't require message structure analysis.

However, when both the Service Interface and the Software Component exist but the ESR object can't be fetched, Migration Assessment reports an inconsistency error, which indicates that the ESR reference is missing or the Software Component ID is empty.

</td>
</tr>
<tr>
<td valign="top">

Dynamic Receiver Determination Evaluation

</td>
<td valign="top">

When receivers are determined dynamically in the Integration Configuration Object \(ICO\) or in Receiver Determination, the Migration Assessment cannot determine the exact number of receivers. This may happen in the following integration scenarios:

-   XPath-based receiver conditions

    If the receiver conditions in the Integration Configuration Object \(ICO\) or the Receiver Determination use XPath expressions to determine the receiver dynamically, the Migration Assessment cannot determine the exact number of receivers. That happens because the receiver depends on the message payload evaluated at runtime.

-   Extended Receiver Determination with *Allow Arbitrary Receivers*

    If the extended receiver determination in the Integration Configuration \(ICO\) or the Receiver Determination is used together with the option *Allow Arbitrary Receivers*, the number of receivers may be determined dynamically at runtime and can't be fully analyzed during Migration Assessment.


Therefore, in both integration scenarios, the interface is partially assessed and receiver-specific rules are excluded.

</td>
</tr>
<tr>
<td valign="top">

Performance Data

</td>
<td valign="top">

Migration Assessment cannot collect performance metrics \(such as message size or processing time\) for Integration Engine \(ABAP\) components through the available APIs. Therefore, performance data for these components isn't included in the extracted results.

For Adapter Engine \(JAVA\) components, to include performance details in the extraction, administrators must enable performance monitoring in SAP Process Orchestration as described in SAP Note [3300008](https://me.sap.com/notes/3300008) and Monitoring Performance.

For synchronous messages, message count logging must be enabled in the SAP NetWeaver Administrator \(NWA\) as per the SAP Note [2442373](https://me.sap.com/notes/2442373).

</td>
</tr>
<tr>
<td valign="top">

Custom Adapters, Custom Adapter Modules, and Attributes

</td>
<td valign="top">

The Migration Assessment does not assess custom adapters, custom adapter modules, or their specific configuration attributes. The custom adapters and custom adapter modules are identified as part of the integration design, but their source code, internal logic and parameter-level settings aren't analyzed. Only standard SAP adapters are evaluated in detail.

You can consider a detailed analysis directly in the SAP Process Orchestration system and the migration effort needs to be estimated separately.

</td>
</tr>
<tr>
<td valign="top">

B2B, BRM, and BPM Objects

</td>
<td valign="top">

The Migration Assessment does not assess B2B scenarios and Business Rules Management \(BRM\) objects. These components are entirely out of scope for the Migration Assessment.

For Business Process Management \(BPM\) and Cross-Component Business Process Management \(ccBPM\) processes, the Migration Assessment can identify the BPM/ccBPM name and the associated integration scenario. However, it can't read or analyze the internal BPM or ccBPM process logic. In this case, you can consider a detailed analysis directly in the SAP Process Orchestration system and the migration effort needs to be estimated separately.

</td>
</tr>
<tr>
<td valign="top">

Java, XSLT, Function Libraries, and UDF Dependencies

</td>
<td valign="top">

The Migration Assessment identifies objects such as Java mappings, XSLT, function libraries, and user-defined functions \(UDFs\), but it does not recursively analyze their dependencies.

> ### Example:  
> If a Java Mapping internally calls another Java class or Function Library, the dependent code is not checked during the assessment.



</td>
</tr>
<tr>
<td valign="top">

Message Throughput Statistics

</td>
<td valign="top">

During the migration assessment, the following message appears when a 1:1 relationship between the interface and the message from the *Message Monitor* can't be established: “Multiple Scenario Identifiers are identified for the same interface while counting the message throughput. Reported values may be inaccurate.”

This usually happens when you have different variations of the same sender interface \(for example, with a sender wildcard or same sender with different virtual receivers\). As a result, the reported message throughput may not accurately reflect the actual usage for these scenarios.

</td>
</tr>
<tr>
<td valign="top">

Configuration Scenario Analyses \(ICO and Receiver Determination\)

</td>
<td valign="top">

Migration Assessment evaluates the configuration objects individually, but it doesn't identify how many Configuration Scenarios exist in the system, nor does it determine which objects belong together for a specific interface. As a result, each object is analyzed independently based on its metadata which means that the Migration Assessment output remains object-based rather than scenario-based.



</td>
</tr>
<tr>
<td valign="top">

Interface Dependencies

</td>
<td valign="top">

Migration Assessment cannot identify dependencies between different interfaces within the landscape and it does not perform business process analysis to check dependent interfaces. Additional manual analysis is required to understand and validate interfaces dependencies that may exist during the migration strategy planning.

</td>
</tr>
<tr>
<td valign="top">

Supported SAP Process Orchestration Versions

</td>
<td valign="top">

Systems running on SAP Process Orchestration versions below the ones supported by Migration Assessment cannot be assessed.

Supported versions:

-   7.31 SP28 and above

-   7.40 SP23 and above

-   7.50 SP06 and above


> ### Note:  
> For the Process Orchestration version 7.50 \(SP06 to SP09\), make sure to implement the patch as described in the SAP Note [2456339](https://me.sap.com/notes/2456339).



</td>
</tr>
</table>

