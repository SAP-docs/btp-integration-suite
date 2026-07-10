<!-- loio7e704f78272848b98fee5942a3697bec -->

# Design Guidelines for API Artifact

A set of best practices to ensure that APIs are designed for consistency, scalability, security, and ease of maintenance within SAP Integration Suite.

By following a defined set of design guidelines, developers can build scalable and efficient API artifacts that are easier to manage, monitor, and extend over time. These guidelines cover key areas such as modular design, error handling, security, and performance optimization—ensuring best practices are consistently applied across all components of an API artifact.

> ### Note:  
> Only sub-categories marked as Yes are shown under Design Guidelines in the API artifact property sheet.

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

[Ensure Upgrade Readiness](ensure-upgrade-readiness-6adb0ca.md) 

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

[Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md) 

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

[Optimize Memory Footprint](optimize-memory-footprint-dc24074.md) 

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

[Run an Integration Flow Under Well-Defined Boundary Conditions](run-an-integration-flow-under-well-defined-boundary-conditions-f8cf974.md) 

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

[General Scripting Guidelines](general-scripting-guidelines-fcbf0f2.md) 

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

[Apply the Highest Security Standards](apply-the-highest-security-standards-201fd43.md) 

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

No

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

[Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md) 

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

[Handle Errors Gracefully](handle-errors-gracefully-42c95f7.md) 

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

[Relax Dependencies to External Components](relax-dependencies-to-external-components-3ea1e33.md) 

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

[Keep Readability in Mind](keep-readability-in-mind-578fa77.md) 

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

No

</td>
</tr>
<tr>
<td valign="top">

Externalize Volatile Configurations for Sender Adapters

</td>
<td valign="top">

No

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

For more detailed guidance, see [Integration Flow Design Guidelines](integration-flow-design-guidelines-6803389.md).

