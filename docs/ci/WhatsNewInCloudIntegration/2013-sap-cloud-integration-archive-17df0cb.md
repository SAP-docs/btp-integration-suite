<!-- loio17df0cb6e8444c91ab6b111d0a6d5bef -->

# 2013 SAP Cloud Integration \(Archive\)

The following features are new or have been enhanced in the current version of SAP Cloud Integration \(for process integration\).



## 07 December 2013

These release notes correspond to the customer shipment on **07.12.2013**.

Planned future shipments: 01-16-2014

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Related Software Versions**


<table>
<tr>
<th valign="top">

Software Version \(Runtime\)

</th>
<th valign="top">

Link to Eclipse Update Site

</th>
</tr>
<tr>
<td valign="top">

1.5.\*

\(is provided by SAP\)

> ### Note:  
> You can check for this software version in the following way: Open the Integration Operations perspective in Eclipse and in the Node Explorer position the cursor on the tenant name. Then the software version is displayed in a tooltip.



</td>
<td valign="top">

1.5.\*

[https://tools.hana.ondemand.com/juno](https://tools.hana.ondemand.com/juno)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

</td>
</tr>
</table>

**SAP Cloud Integration Spaces \(Web UI\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Viewing Integration Packages

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

You can now download all artifacts at one go

</td>
</tr>
<tr>
<td valign="top">

Monitoring \(SAP Cloud Integration Spaces\)

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

There are the following enhancements in the SAP Cloud Integration Spaces Monitoring application:

-   Autorefresh on dashboard/start page
-   Displaying notifications in a separate bar at the bottom of the Web UI
-   Restarting Integration Artifacts
-   Dropdown listbox in Artifact view that allows to open detail page for another artifact
-   Tooltips for message errors
-   Highlighted information on message errors in the message processing log
-   Cancelling erroneous messages



</td>
</tr>
</table>

**Integration Designer \(Eclipse Feature\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Assigning the Sender and Receiver Participants

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

You can authenticate a sender system having any SOAP \(SOAP 1.x, Plain SOAP, SOAP WS-RM\) or IDoc \(IDoc SOAP\) connector using Basic Authentication apart from the already available feature of authenticating using an authorized client certificate.

</td>
</tr>
<tr>
<td valign="top">

Defining Splitter

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

Two new type of splitters, called the General Splitter and Iterative Splitter, are available in addition to the existing IDoc Splitter and PKCS\#7/CMS Signature-Content Splitter..

</td>
</tr>
<tr>
<td valign="top">

Defining Content Modifier

</td>
<td valign="top">

Renamed

</td>
<td valign="top">

Content Enricher is now renamed to Content Modifier. The feature functionality has no change. It’s corresponding pattern is no more available in the Integration Flow wizard during the integration flow creation.

</td>
</tr>
</table>

**Integration Operations \(Eclipse Feature\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Deploying a Basic Authentication Artifact

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

The wizard for Basic Authentication \(CREDENTIALS\) artifacts has been enhanced to support scenarios with basic authentication \(receiver side/outbound\).

</td>
</tr>
<tr>
<td valign="top">

Properties View for Deployed Artifacts

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

When you select a Basic Authentication artifact in the Deployed Artifacts editor, the Properties view shows additional information on the artifact.

</td>
</tr>
<tr>
<td valign="top">

Monitoring External Reachability of Runtime Node

</td>
<td valign="top">

New

</td>
<td valign="top">

You can monitor if runtime nodes \(assigned to the tenant management node\) can be reached by external calls.

For this purpose, an external SSL call of a runtime node is simulated and monitored using a specific component in the Component Status view.

</td>
</tr>
</table>



## 09 November 2013

These release notes correspond to the customer shipment on **09.11.2013**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Related Software Versions**


<table>
<tr>
<th valign="top">

Software Version \(Runtime\)

</th>
<th valign="top">

Link to Eclipse Update Site

</th>
</tr>
<tr>
<td valign="top">

1.4.\*

\(is provided by SAP\)

> ### Note:  
> You can check for this software version in the following way: Open the Integration Operations perspective in Eclipse and in the Node Explorer position the cursor on the tenant name. Then the software version is displayed in a tooltip.



</td>
<td valign="top">

1.4.\*

[https://tools.hana.ondemand.com/juno](https://tools.hana.ondemand.com/juno)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

</td>
</tr>
</table>

**SAP Cloud Integration Spaces \(Web UI\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Deploying Data Flows

</td>
<td valign="top">

New

</td>
<td valign="top">

You can deploy data flows through the integrated Data Services application available on SAP Cloud Integration Spaces.

</td>
</tr>
<tr>
<td valign="top">

Monitoring \(SAP Cloud Integration Spaces\)

</td>
<td valign="top">

New

</td>
<td valign="top">

A new section on SAP Cloud Integration Spaces provides capabilities to monitor SAP Cloud Integration clusters and message processing. In particular, the following information can be accessed:

-   Information on the runtime status of deployed integration content
-   Information on the status of messages processed on a tenant cluster



</td>
</tr>
</table>

**Integration Designer \(Eclipse Feature\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Defining Gateway

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

You can create conditions for non-XML messages. Such conditions are allowed for header expressions using a set of supported operators and regex.

</td>
</tr>
<tr>
<td valign="top">

Creating Multi Mappings

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

This is an enhancement of the mapping feature. You can now perform mapping using multiple source and target messages of type XSD or WSDL.

</td>
</tr>
</table>

**Integration Operations \(Eclipse Feature\)**


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Type of Change

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Deployed Artifacts Editor

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

For security artifacts deployed on a tenant of a cluster based on the 1.4.\* software version, the node type TENANT\_MGMT is displayed in the Deployed Artifacts editor.

</td>
</tr>
<tr>
<td valign="top">

Component Status View

</td>
<td valign="top">

Enhanced

</td>
<td valign="top">

The new sub system *Persistence* has been introduced. It allows you to monitor for each node if the write access to the data base works correctly.

</td>
</tr>
</table>

