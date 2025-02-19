<!-- loio417f82b21c804aa5910db908733c5d59 -->

# Limit Size of Deployed Integration Content

Limit size of deployed integration content to avoid exceeding the storage capacity of the system.

With each integration artifact that you deploy on the tenant, you consume a portion of the limited storage capacity. All deployed artifacts \(for example, integration flows\) as well as the objects they use \(for example, scripts\) contribute to the percentage of claimed storage space. Model your integration content in a way that minimizes the impact on this capacity. In this way, you can avoid exceeding this storage capacity.

The following measures can help to optimize the usage of tenant storage capacity used by deployed integration content:

-   Undeploy all integration content that is not used.

-   Model your integration scenarios in such a way that as much integration content as possible is reused.

    Adhering to this guideline also has a positive impact on aspects related to the lifecycle and governance of your integration content. For example, when you maximize reuse, the effort to update your integration content is minimized.

    With the following measures you can improve your reuse strategy:

    -   Outsource a task that is used in multiple places in the scenario to a "generic" integration flow. The latter one is then called from different integration flows using the ProcessDirect adapter.

        See also: [Outsource Integration Logic into Separate Integration Flows](outsource-integration-logic-into-separate-integration-flows-0bcf78d.md)

    -   Reuse mappings and scripts as artifacts.

        See also:

        [Creating Message Mapping as an Artifact](creating-message-mapping-as-an-artifact-1d52a7b.md)

        [Developing Script and Script Collection](developing-script-and-script-collection-e60f706.md)


-   Reuse custom libraries.

    While direct reuse of a library isn't currently supported, you can still reuse scripts that consume the library by adding them to a script collection. This can be beneficial in situations where sharing functionality based on the library, rather than the library itself, is feasible.


The following predefined integration flows exemplify how to maximize content reusability.

**Examples How to Optimize Reuse**


<table>
<tr>
<th valign="top">

Example Integration Flow

</th>
<th valign="top">

Reuse Method

</th>
</tr>
<tr>
<td valign="top">

[JMS Send Step in Local Integration Process](jms-send-step-in-local-integration-process-a5644c8.md) 

</td>
<td valign="top">

The main integration process contains two multicast branches. From each branch, a local integration process is called.

The local integration process contains the following steps: encoding the content and storing it in a JMS queue.

</td>
</tr>
<tr>
<td valign="top">

[Handle Exceptions in Dependent Integration Flows \(Simple Scenario\)](handle-exceptions-in-dependent-integration-flows-simple-scenario-984e51a.md) 

</td>
<td valign="top">

Exception handling is handled by a separate integration flow which is called from the main integration flow using the ProcessDirect adapter.

</td>
</tr>
</table>

> ### Note:  
> The following SAP Community blog provides provides you with a summary of some measures to reduce the size of deployed integration content: [Cloud Integration – Content Size Limits](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-content-size-limits/ba-p/13469116).

