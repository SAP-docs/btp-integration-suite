<!-- loio9ddb257eb17744a6b861df300a59df9a -->

# Migration Approaches

Learn the details and differences of each approach to help determine which one best suits your migration needs.



<a name="loio9ddb257eb17744a6b861df300a59df9a__section_xdq_zk3_w2c"/>

## Standard Approach

Use this approach if you only want to migrate a few integration scenarios to Cloud Integration. You will be able to create individual integration flows for each of your original integration scenarios easily. For more information, see [Migration tool in Cloud Integrationof SAP Integration Suite](https://community.sap.com/t5/technology-blogs-by-sap/migration-tool-in-cloud-integration-capability-of-sap-integration-suite/ba-p/13555109) \(SAP Community Blog\).



## Pipeline Approach

Use this approach to migrate a large number of integration scenarios quickly with reduced effort and cost. The integration scenarios in Cloud Integration will be setup similarly to how messages are processed in SAP Process Integration and SAP Process Orchestration, in pipelines. For more information on the concept, see [Pipeline Concept](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/pipeline-concept) and [Introducing the new pipeline concept in SAP Cloud Integration](https://community.sap.com/t5/technology-blogs-by-sap/introducing-the-new-pipeline-concept-in-cloud-integration/ba-p/13639651) \(SAP Community Blog\).



## Quick Comparison: Standard vs Pipeline Approach

****


<table>
<tr>
<th valign="top">

Criteria

</th>
<th valign="top">

Standard Approach

</th>
<th valign="top">

Pipeline Approach

</th>
</tr>
<tr>
<td valign="top">

Patterns

</td>
<td valign="top">

Point-to-point Synchronous and Asynchronous, Recepeint List, Content-based Routing

</td>
<td valign="top">

Point-to-point Asynchronous, Recipient List, Content-based Routing

</td>
</tr>
<tr>
<td valign="top">

Reuse of artifacts \(Data Type, Message Type, mappings, etc.\)

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Error handling

</td>
<td valign="top">

Stub only, needs to be manually modelled

</td>
<td valign="top">

Out of the box and custom exits

</td>
</tr>
<tr>
<td valign="top">

Monitoring and Operation

</td>
<td valign="top">

SAP headers supported

</td>
<td valign="top">

Isolate error into pipeline steps; SAP headers and custom header properties supported; processing log with further information supported

</td>
</tr>
<tr>
<td valign="top">

Artifacts \(Data Type, Message Type, mappings, etc.\) generated per integration scenario

</td>
<td valign="top">

One single integration flow

</td>
<td valign="top">

Multiple integration flows/ Partner Directory entries

</td>
</tr>
<tr>
<td valign="top">

Required JMS resources

</td>
<td valign="top">

Own queue for each async integration scenario

</td>
<td valign="top">

Reduced number of queues shared across multiple scenarios

</td>
</tr>
<tr>
<td valign="top">

Single XI and IDoc endpoint

</td>
<td valign="top">

Needs to be modelled manually

</td>
<td valign="top">

Out of the box

</td>
</tr>
</table>



## Detailed Comparison: Standard vs Pipeline Approach

**Detailed Comparison**


<table>
<tr>
<th valign="top">

Criteria

</th>
<th valign="top">

Standard Approach

</th>
<th valign="top">

Pipeline Approach

</th>
</tr>
<tr>
<td valign="top">

Communication Patterns

</td>
<td valign="top">

Supports both synchronous and asynchronous communication scenarios.

</td>
<td valign="top">

Framework for processing asynchronous messages in a common way, providing sophisticated restart and error handling capabilities out of the box.

</td>
</tr>
<tr>
<td valign="top">

Exception Handling

</td>
<td valign="top">

Only generates an exception subprocess stub, requiring you to model your own error handling logic for each integration scenario.

</td>
<td valign="top">

Features built-in exception handling, including automatic and manual restart options, and an extension point to implement custom exception processes. This exception handler can be reused across all integration scenarios.

</td>
</tr>
<tr>
<td valign="top">

Content-based routing

</td>
<td valign="top">

For recipient list and content-based routing scenarios, the routing conditions can be directly maintained in the generated integration flow

</td>
<td valign="top">

For recipient list and content-based routing scenarios, this approach implements routing conditions using an XSLT mapping that is uploaded to the Partner Directory. While the Partner Directory UI provides easy access to all generated entries, it does not support direct maintenance of routing conditions. Therefore, to modify the routing conditions, you must download the XSLT, make the necessary changes, and then upload the revised XSLT.

</td>
</tr>
<tr>
<td valign="top">

Monitoring

</td>
<td valign="top">

Needs manual modelling for each scenario.

</td>
<td valign="top">

Different measures have been implemented improving the monitoring of the message processing such as the use of SAP headers, an extension point for supporting custom header properties, a processing log providing detailed information about all pipeline steps, etc. Furthermore, the pipeline model itself with its set of generic integration flows and the usage of the Partner Directory simplifies operation by separating the errors into the different pipeline steps and by reducing the number of JMS queues overall required.

</td>
</tr>
</table>

