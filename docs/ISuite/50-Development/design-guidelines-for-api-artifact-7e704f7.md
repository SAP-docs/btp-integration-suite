<!-- loio7e704f78272848b98fee5942a3697bec -->

# Design Guidelines for API Artifact

A set of best practices to ensure that APIs are designed for consistency, scalability, security, and ease of maintenance within SAP Integration Suite.

By following a defined set of design guidelines, developers can build scalable and efficient API artifacts that are easier to manage, monitor, and extend over time. These guidelines cover key areas such as modular design, error handling, security, and performance optimization—ensuring best practices are consistently applied across all components of an API artifact.

****


<table>
<tr>
<th valign="top">

Design Guidelines

</th>
<th valign="top">

Sub-Category

</th>
<th valign="top">

Does This Apply to APIs?

</th>
<th valign="top">

Important Links

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Ensure Upgrade Readiness - Groovy Script

</td>
<td valign="top">

Use recommended libraries and proxy-based classes

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="3">

[Ensure Upgrade Readiness](https://help.sap.com/docs/integration-suite/sap-integration-suite/ensure-upgrade-readiness?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Include only used import statements

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use only supported classes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Define Proper Transaction Handling

</td>
<td valign="top">

Avoid mixing JDBC and JMS transactions

</td>
<td valign="top">

No

</td>
<td valign="top" rowspan="3">

[Define Proper Transaction Handling](https://help.sap.com/docs/integration-suite/sap-integration-suite/define-proper-transaction-handling?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Keep The Transactions Shorter

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Transactional processing set for Parallel Processing

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Optimize Memory Footprint

</td>
<td valign="top">

Use ByteArray As Output Type To Process Large Messages

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="3">

[Optimize Memory Footprint](https://help.sap.com/docs/integration-suite/sap-integration-suite/optimize-memory-footprint?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Reset Data For Every Branch

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use XPATH Condition Appropriately

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Run an Integration Flow or an API Under Well-Defined Boundary Conditions

</td>
<td valign="top">

Optimize the Artifact Design For Streaming

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="5">

[Run an Integration Flow Under Well-Defined Boundary Conditions](https://help.sap.com/docs/integration-suite/sap-integration-suite/run-integration-flow-under-well-defined-boundary-conditions?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Manage Large Batch Sizes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Limit Size of Incoming Messages

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Manage Timeout For SuccessFactors

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Avoid Using a Generic User Role for Sender-Side Authorization

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top" rowspan="9">

Scripting Guidelines

</td>
<td valign="top">

Use of DocumentBuilderFactory without disallowing the doctype declaration

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="9">

[General Scripting Guidelines](https://help.sap.com/docs/integration-suite/sap-integration-suite/general-scripting-guidelines?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Avoid Using Default Timezone

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Avoid Creating MPL Attachments

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use of JsonSlurper

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use of XMLSlurper

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use Only Supported External Libraries

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Static analysis of Groovy scripts

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Avoid Using Eval Classes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Avoid Accessing Secure Parameter

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Apply the Highest Security Standards

</td>
<td valign="top">

Use Secure Authentication Methods

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="4">

[Apply the Highest Security Standards](https://help.sap.com/docs/integration-suite/sap-integration-suite/apply-highest-security-standards?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Upload WSDLs as Artifact Resources

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use Secure Protocols

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use CSRF Protection

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Anticipate Message Throughput When Choosing a Storage Option

</td>
<td valign="top">

Unexpected Data Growth

</td>
<td valign="top">

Yes

</td>
<td valign="top">

[Anticipate Message Throughput When Choosing a Storage Option](https://help.sap.com/docs/integration-suite/sap-integration-suite/anticipate-message-throughput-when-choosing-storage-option?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Handle Errors Gracefully

</td>
<td valign="top">

Handle Exceptions

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="2">

[Handle Errors Gracefully](https://help.sap.com/docs/integration-suite/sap-integration-suite/handle-errors-gracefully?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Handle Exceptions in Local Integration Process

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Relax Dependencies to External Components

</td>
<td valign="top">

Apply Retry Pattern With JMS Queue

</td>
<td valign="top">

No

</td>
<td valign="top">

[Relax Dependencies to External Components](https://help.sap.com/docs/integration-suite/sap-integration-suite/relax-dependencies-to-external-components?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Keep Readability in Mind

</td>
<td valign="top">

Define Identifiers To Search In Message Processing Logs

</td>
<td valign="top">

Yes

</td>
<td valign="top" rowspan="5">

[Keep Readability in Mind](https://help.sap.com/docs/integration-suite/sap-integration-suite/keep-readability-in-mind?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Remove Unused Artifact Flow Steps

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Externalize Volatile Configurations for Receiver Adapters

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Externalize Volatile Configurations for Sender Adapters

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Use Only Allowed Number of Pools and Flow Steps

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

For more detailed guidance, refer to the [Integrations and API Design Guidelines](https://help.sap.com/docs/integration-suite/sap-integration-suite/integration-flow-design-guidelines?version=CLOUD) section.

**Related Information**  


[Create an API Artifact](create-an-api-artifact-c2fe62c.md "Create an API artifact to securely expose backend services, apply consistent governance by adding security and traffic management policies, and gain better visibility and control over how your APIs are accessed and used.")

[Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md "Add a resource to refer to individual endpoints or services.")

[Copy an API Artifact](copy-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API artifact but with some modifications or variations.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policies.")

[Deploy an API Artifact](deploy-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Externalize Parameter for API Artifact](externalize-parameter-for-api-artifact-ce0a468.md "You can use the externalization feature to define API policies and integration flows that can retrieve externalized configuration values during runtime. These parameters can be utilized later without modifying the standard API artifact.")

