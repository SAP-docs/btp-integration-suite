<!-- loio2f5d4f15e3944e7d86109406afbaf054 -->

# 2016 SAP Cloud Integration \(Archive\)



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_l4d_www_rdb"/>

## 17 December 2016

These release notes correspond to the customer shipment on **2016-12-17**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.25.\***

Node Assembly \(Cluster 1.x\): **1.44.\***

Node Assembly \(Cluster 2.x\): **2.22.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Enhanced authorization option in sender adapters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For the following adapter types, the authorization option has been enhanced to allow also to enter custim roles. The following adapter types have been enhanced:

-   HTTPS sender adapter

-   AS2 sender adapter




</td>
<td valign="top">

[HTTPS Sender Adapter](../Development/https-sender-adapter-0ae4a78.md)

 <?sap-ot O2O class="- topic/xref " href="63a96540c8494b578ec657bdfa5be6b8.xml" text="" desc="" xtrc="xref:9" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Dynamically provide Data Store Name



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now dynamically provide the Data Store Name for the transient data store using headers.



</td>
<td valign="top">

[Define Data Store Operations](../Development/define-data-store-operations-79f63a4.md) 



</td>
</tr>
<tr>
<td valign="top">

Technical information available for integration flow elements



</td>
<td valign="top">

New



</td>
<td valign="top">

This feature enables you to view the technical information like step id and version of a component \(element\). For channels, this technical information can be accessed using context menu. For other elements you can click on the information icon in the editor when you move the cursor on the component \(element\).



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Message Monitoring user interface enhanced by paging



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now browse through the list of processed messages using a paging option.



</td>
<td valign="top">

[Monitor Message Processing](../Operations/monitor-message-processing-314df3f.md) 



</td>
</tr>
<tr>
<td valign="top">

*Update* operation support for SuccessFactors OData V4 receiver



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use the SuccessFactors OData V4 adapter to perform *Update* operation.



</td>
<td valign="top">

[SuccessFactors OData V4 Receiver Adapter](../Development/successfactors-odata-v4-receiver-adapter-cd091fc.md) 



</td>
</tr>
<tr>
<td valign="top">

Context switch in source message for mapping



</td>
<td valign="top">

New



</td>
<td valign="top">

You can change the context of a field in the source message of the mapping definition reource.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3f2f4bb739b84bf48154d6734869a992.xml" text="" desc="" xtrc="xref:13" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Transaction handling for integration process and local integration process



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now define \(on integration process and local integration process level\) that the message is processed within one transaction.



</td>
<td valign="top">

[Define Transaction Handling](../Development/define-transaction-handling-2a5d4bc.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Enhanced authorization option in sender adapters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For the following adapter types, the authorization option has been enhanced to allow also to enter custim roles. The following adapter types have been enhanced:

-   HTTPS sender adapter

-   AS2 sender adapter




</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="96c4de6cc2224e2a8eac6ecef7e562ce.xml" text="" desc="" xtrc="xref:15" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="a5eebca5329749669660b1779202b4c0.xml" text="" desc="" xtrc="xref:16" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Dynamically provide Data Store Name



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now dynamically provide the Data Store Name for the transient data store using headers.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="249800a2ce894867bb6dde96b5dc5df3.xml" text="" desc="" xtrc="xref:17" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Tracing retention period modified



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Post message processing, the trace data is deleted after 60 minutes.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="866b6a94a074487384a21377ec9f2eb2.xml" text="" desc="" xtrc="xref:18" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

*Update* operation support for SuccessFactors OData V4 receiver



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use the SuccessFactors OData V4 adapter to perform *Update* operation.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9c915cc929d84559997c12e18c74e9f0.xml" text="" desc="" xtrc="xref:19" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Transaction handling for integration process and local integration process



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now define \(on integration process and local integration process level\) that the message is processed within one transaction.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="e4630de9a8314848b73555e0b0c35d7e.xml" text="" desc="" xtrc="xref:20" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
</table>

**SAP Cloud Integration API**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Deploy integration artifacts with OData API



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now deploy an integration artifact \(integration flow, value mapping, or OData API\) using the OData API.



</td>
<td valign="top">

[OData API](../Development/odata-api-a617d6f.md) 



</td>
</tr>
</table>

**Additional Information**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_ysv_bxw_rdb"/>

## 19 November 2016

These release notes correspond to the customer shipment on **2016-11-19**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.24.\***

Node Assembly \(Cluster 1.x\): **1.43.\***

Node Assembly \(Cluster 2.x\): **2.21.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeploy Integration Flows with Run Once Setting in Timer or Scheduler

If you have deployed integration flows with *Run Once* option selected in *Timer*/*Scheduler*, you have to manually *Undeploy* the integration flows and *Deploy* them again. This prevents the integration flow from triggering message after software update.



### Redeployment of Integration Flows Might be Required in These Cases

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Inbound authorization for SOAP-based adapters changed



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Configuration of inbound authorization for SOAP-based adapters \(SOAP 1.x, SAP RM and IDoc\) is now accomplished per adapter. Accordingly, inbound authorization cannot be performed anymore in the sender participant.



</td>
<td valign="top">

[SOAP \(SAP RM\) Adapter](../Development/soap-sap-rm-adapter-6bd724f.md)

 <?sap-ot O2O class="- topic/xref " href="efff064fdb9140adbc4e195fdf906e3e.xml" text="" desc="" xtrc="xref:30" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="9597227a3a044904988fb9dca54aaceb.xml" text="" desc="" xtrc="xref:31" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

[Assign Sender and Receiver Components](../Development/assign-sender-and-receiver-components-f0eb056.md)

Changed procedures:

[Setting Up Inbound HTTP Connections \(with Basic Authentication\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-basic-authentication-neo-environment-391c45c.md)

[Setting Up Inbound HTTP Connections \(with Certificate-to-User Mapping\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-certificate-to-user-mapping-neo-environment-9949c61.md)

[Setting Up Inbound HTTP Connections \(with Client Certificate Authentication\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-client-certificate-authentication-neo-environmen-057f4a7.md)



</td>
</tr>
<tr>
<td valign="top">

Canceling a message not possible any more



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The feature to cancel messages has been removed from the Message Monitor.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Example for the HTTP receiver query string



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now find an example how to use the query string in the HTTP Receiver Adapter.



</td>
<td valign="top">

[HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md) 



</td>
</tr>
<tr>
<td valign="top">

Timer/Scheduler *Run Once* Enhancement



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

This fix ensures that integration flows with *Run Once* setting in *Timer*/*Scheduler* trigger messages only when the integration flow bundles are deployed.



</td>
<td valign="top">

[Define a Timer Start Event](../Development/define-a-timer-start-event-ae14ad7.md) 



</td>
</tr>
<tr>
<td valign="top">

Assign mapping definition resource



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now assign a mapping definition resource to the message mapping step in addition to creating a new mapping definition resource.



</td>
<td valign="top">

[Working with Mapping](../Development/working-with-mapping-68d816a.md) 



</td>
</tr>
<tr>
<td valign="top">

Pass filter conditions via header or property for SuccessFactors SOAP asynchronous operations



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now pass filter conditions via header or properties while performing asynchronous or ad-hoc query using SuccessFactors SOAP adapter.



</td>
<td valign="top">

[SuccessFactors SOAP Adapter](../Development/successfactors-soap-adapter-28b29d6.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Inbound authorization for SOAP-based adapters changed



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Configuration of inbound authorization for SOAP-based adapters \(SOAP 1.x, SAP RM and IDoc\) is now accomplished per adapter. Accordingly, inbound authorization cannot be performed anymore in the sender participant.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="45a7fe20558b4b188cfc93180be982be.xml" text="" desc="" xtrc="xref:40" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="16b2960160204db8a9c6098634593f72.xml" text="" desc="" xtrc="xref:41" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:42" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:43" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Canceling a message not possible any more



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The feature to cancel messages has been removed from the Message Monitor.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Technical information available for integration flow elements



</td>
<td valign="top">

New



</td>
<td valign="top">

This feature enables you to view the technical information like step id and version of a component \(element\). For channels, this technical information can be accessed using context menu. For other elements you can click on the information icon in the editor when you move the cursor on the component \(element\).



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Example for the HTTP receiver query string



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now find an example how to use the query string in the HTTP Receiver Adapter



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:44" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Timer/Scheduler *Run Once* Enhancement



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

This fix ensures that integration flows with *Run Once* setting in *Timer*/*Scheduler* trigger messages only when the integration flow bundles are deployed.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="27f4f030b2cc432f93869f9692f5f5c2.xml" text="" desc="" xtrc="xref:46" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Pass filter conditions via header or property for SuccessFactors SOAP asynchronous operations



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now pass filter conditions via header or properties while performing asynchronous or ad-hoc query using SuccessFactors SOAP adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="aad94bc587904765b64f1bbbf80aac19.xml" text="" desc="" xtrc="xref:47" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Server certificate chain enhanced by SAN



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The server certificate chain now also contains the SAN \(SubjectsAlternativeNames\).



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08adad0516e347dbb0539fc488092a8f.xml" text="" desc="" xtrc="xref:48" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**SAP Cloud Integration API**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

OData API has been enhanced



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The OData API has been enhanced by the following features:

-   A new entity `MessageProcessingLogAttachmentallows` you to access MPL attachments.

-   A new entity `MessageStoreEntryAttachmentProperties` you to access properties on a message store entry attachment.

-   You can now undeploy an integration artifact by applying the DELETE operation on an `IntegrationRuntimeArtifact` instance.




</td>
<td valign="top">

[OData API](../Development/odata-api-a617d6f.md) 



</td>
</tr>
</table>

**Additional Information**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Configuring OAuth for inbound communication



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now configure OAuth for inbound communication.



</td>
<td valign="top">

[Setting Up Inbound HTTP Connections \(with OAuth\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-oauth-neo-environment-e5cb7ea.md) 



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_l5x_bxw_rdb"/>

## 22 and 10, October 2016

These release notes correspond to the customer shipment on **2016-10-22**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.23.\***

Node Assembly \(Cluster 1.x\): **1.42.\***

Node Assembly \(Cluster 2.x\): **2.20.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Script feature allows usage of some more methods



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now add, set, get, remove headers to/from an attachment and add, set attachment objects as a map,using message processing log through some new methods.



</td>
<td valign="top">

[Define a Local Script Step](../Development/define-a-local-script-step-03b32eb.md)



</td>
</tr>
<tr>
<td valign="top">

EDI Splitter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now split and validate inbound bulk EDI messages and route it to specific trading partners.



</td>
<td valign="top">

[Define EDI Splitter](../Development/define-edi-splitter-584a3be.md) 



</td>
</tr>
<tr>
<td valign="top">

Proxy Type



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now configure a proxy server to AS2 receiver communication channel.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="63a96540c8494b578ec657bdfa5be6b8.xml" text="" desc="" xtrc="xref:60" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Timer/Scheduler *Run Once* setting



</td>
<td valign="top">

Enhancement



</td>
<td valign="top">

If you configure the *Timer* or *Scheduler* with *Run Once* setting, message is triggered only when you deploy the integration flow. Restarting the integration flow bundle will not trigger a message.



</td>
<td valign="top">

[Define a Timer Start Event](../Development/define-a-timer-start-event-ae14ad7.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Script feature allows usage of some more methods



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now add, set, get, remove headers to/from an attachment and add, set attachment objects as a map,using message processing log through some new methods.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="905b24171cc746ef9069939ff3b536db.xml" text="" desc="" xtrc="xref:63" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Trace Configuration Editor



</td>
<td valign="top">

New



</td>
<td valign="top">

Integration flow developers and/or tenant admin personas can now enable tracing for specific integration flows using the self service feature. This feature is available in the *Trace Configuration* tab in *Integration Operations* perspective. You do not have to depend on SAAS admin for enabling trace anymore.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a83ce8c016a8467fa6a165ce9da5a40c.xml" text="" desc="" xtrc="xref:64" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Timer/Scheduler *Run Once* setting



</td>
<td valign="top">

Enhancement



</td>
<td valign="top">

If you configure the *Timer* or *Scheduler* with *Run Once* setting, message is triggered only when you deploy the integration flow. Restarting the integration flow bundle will not trigger a message.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="27f4f030b2cc432f93869f9692f5f5c2.xml" text="" desc="" xtrc="xref:65" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
</table>

**SAP Cloud Integration API**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

OData API extended by new entities



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The OData API has been extended by the following entities:

-   `MessageProcessingLogAdapterAttribute`

    Allows to access adapter-specific attributes in line with message processing log data.

-   `IntegrationRuntimeArtifact` and `RuntimeArtifactErrorInformation`

    Addresses deployed integration artifacts \(such as integration flows, value mappings or OData APIs\) and related error information.




</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9e990d5d0a1e438dbb3675d43a8f91c3.xml" text="" desc="" xtrc="xref:66" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="cb643921a2ab4a4d8c5f7fc092120811.xml" text="" desc="" xtrc="xref:67" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
</table>

These release notes correspond to the customer shipment on **2016-09-24**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.22.\***

Node Assembly \(Cluster 1.x\): **1.41.\***

Node Assembly \(Cluster 2.x\): **2.19.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

ODC Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

ODC adapter enables you to communicate with systems that expose data through OData channel for SAP Gateway



</td>
<td valign="top">

[ODC Receiver Adapter](../Development/odc-receiver-adapter-3cdbc29.md) 



</td>
</tr>
<tr>
<td valign="top">

General and iterating splitter enhancements



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Line Break has been introduced as new Expression Type to support handling large inbound messages \(non-XML files\).



</td>
<td valign="top">

[Define General Splitter](../Development/define-general-splitter-a6c1916.md)

[Define Iterating Splitter](../Development/define-iterating-splitter-d61d6ec.md)



</td>
</tr>
<tr>
<td valign="top">

MIME multipart encoder step has been enhanced.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically add headers in the MIME multipart encoder step \(*Include Headers* option\). This was up to now only possible by using the Eclipse Integration Designer.



</td>
<td valign="top">

[MIME Multipart Messages](../Development/mime-multipart-messages-3816537.md) 



</td>
</tr>
<tr>
<td valign="top">

Message Monitor, message processing log shows real endpoint URL/name used by SOAP/HTTP/SFTP adapter.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In the Message Monitor, message processing log \(Web UI\), as of now the endpoint URL / name which is actually been used at runtime is being displayed \(property `RealDestinationUrl` for the SOAP/HTTP adapter, property `ProducedFile` for the SFTP adapter\).

You have several options to specify an endpoint URL in a receiver channel.

Examples:

-   HTTP receiver adapter: In the *Address* field you can manually enter an HTTP address or you can dynamically override a manually entered address using the Camel header `CamelHttpUri`.

-   SFTP adapter: In the *File Name* field you can manually enter a file name \(to specify the file to be read from/written to the SFTP server\) or you can dynamically override a manually entered file name using the Camel header `CamelFileName`.




</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Integration Content Monitor now shows detailed error information.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In case an error occurs during the lifecycle of an artifact, detailed information on the error is displayed under *Status Details*.

Before that change, if artifact deployment ran into an error, only the Task Log of the Eclipse Operations tool provided more detailed information on the error.



</td>
<td valign="top">

[Manage Integration Content](../Operations/manage-integration-content-09a7223.md) 



</td>
</tr>
<tr>
<td valign="top">

Option to select product profile during creation of integration flow



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now select product profiles while adding integration flow to integration package.



</td>
<td valign="top">

[Creating an Integration Flow](../Development/creating-an-integration-flow-da53d93.md)



</td>
</tr>
<tr>
<td valign="top">

Configuring Mail sender adapter enabled



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use the mail sender adapter for the following tasks:

-   Downloading e-mails from mailboxes using IMAP or POP3 protocol

-   Accessing the content of the e-mail body

-   Accessing e-mail attachments




</td>
<td valign="top">

[Mail Adapter](../Development/mail-adapter-f1145cc.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Option to select product profile during creation of integration flow



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now select product profiles while creating integration project for an integration flow.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="c8b95b276d6d4feaa19591f7e7af386b.xml" text="" desc="" xtrc="xref:82" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

XSLT Mapping version 1.1 enhancement



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now select mapping source from partner directory and also set header and exchange properties.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="bb7da9abd6914e98ba5b7baacec5c609.xml" text="" desc="" xtrc="xref:83" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Configuring Mail sender adapter enabled



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use the mail sender adapter for the following tasks:

-   Downloading e-mails from mailboxes using IMAP or POP3 protocol

-   Accessing the content of the e-mail body

-   Accessing e-mail attachments




</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:84" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

ODC as a data source



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now create and deploy an OData API that exposes data from an IW\_BEP component on an on-premise SAP Gateway system \(ODC\).



</td>
<td valign="top">

[Importing from ODC](../Development/importing-from-odc-2ecdaf9.md)

[Binding to ODC](../Development/binding-to-odc-460e172.md)



</td>
</tr>
</table>



### Operational Aspects

The list of Subprocessors \(non SAP Affiliates\) for SAP BTP and its services, SAP Financial Services Network, and SAP Cloud Identity Access Governance has been updated. A Subprocessor is any entity or individual, which has or potentially will have access to or process personal data \(as defined in applicable data protection laws\). Find the updated list in the Support Portal at: [Services Subprocessor \(non SAP Affiliates\) List](https://support.sap.com/content/dam/library/SAP%20Support%20Portal/support-programs-services/support-programs/hana-subprocessor/HANA%20Cloud%20Platform%20Services%20Subprocessor%20(non%20SAP%20Affiliates)%20List%20v8.pdf) 

Note that services such as, for example, SAP Cloud Integration service are covered by this document.



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_nhz_bxw_rdb"/>

## 27 August 2016

These release notes correspond to the customer shipment on **2016-08-27**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.21.\***

Node Assembly \(Cluster 1.x\): **1.40.\***

Node Assembly \(Cluster 2.x\): **2.18.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Deleting headers and properties in content modifier



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now not just create but also delete headers and properties.



</td>
<td valign="top">

[Define Content Modifier](../Development/define-content-modifier-8f04a70.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring Message Queues - download improved



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The message download was improved that way that the resulting files have been renamed and attachments are now stored in a separate folder of the .zip file.



</td>
<td valign="top">

[Managing Message Queues](../Operations/managing-message-queues-cdcce24.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring Message Queues - overdue messages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

A new column for overdue messages has been added to the monitor.



</td>
<td valign="top">

[Managing Message Queues](../Operations/managing-message-queues-cdcce24.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Deleting headers and properties in content modifier



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now not just create but also delete headers and properties.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="2c667a12a0a545d2ad4210e070479312.xml" text="" desc="" xtrc="xref:98" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Outbound connectivity test tool enhanced



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Outbound connectivity test for SSL and SSH connections has been enhanced in the following way:

-   During the test of SSL outbound connectivity you have the option to get the certificate chain from the server \(in order to copare it with the keystore entries\). An additional option \(Validate Server Certificate\) has been added to the SSL outbound connectivity test.

-   During the test of SSL outbound connectivity you have the option to verify the host key and adapt the related known\_hosts file accordingly. You can also test SSH connection with the different available authentication options.




</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08adad0516e347dbb0539fc488092a8f.xml" text="" desc="" xtrc="xref:99" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="dcf0040fa517454784669bed3eacfe8b.xml" text="" desc="" xtrc="xref:100" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_jt1_cxw_rdb"/>

## 30 and 16, July 2016

These release notes correspond to the customer shipment on **2016-07-30**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.20.\***

Node Assembly \(Cluster 1.x\): **1.39.\***

Node Assembly \(Cluster 2.x\): **2.17.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

New exchange property to switch off MPL correlation



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In a Content Modifier step, you can set the property `SAP_CorrelateMPLs` to switch off MPL correlation.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3983143d6f8f4ea49461d4f167b5ae6f.xml" text="" desc="" xtrc="xref:108" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Monitoring of Message Queues



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now download a JMS message with attachment\(s\) from the queue monitor.



</td>
<td valign="top">

[Managing Message Queues](../Operations/managing-message-queues-cdcce24.md) 



</td>
</tr>
<tr>
<td valign="top">

SOAP \(SAP RM\) Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now select None as authentication method.



</td>
<td valign="top">

[SOAP \(SAP RM\) Adapter](../Development/soap-sap-rm-adapter-6bd724f.md) 



</td>
</tr>
<tr>
<td valign="top">

Message processing log property SAP\_Receiver can be reset



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now use the Content Modifier to reset the header SAP\_Receiver.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3983143d6f8f4ea49461d4f167b5ae6f.xml" text="" desc="" xtrc="xref:111" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

New exchange property to switch off MPL correlation



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In a Content Modifier step, you can set the property `SAP_CorrelateMPLs` to switch off MPL correlation.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

SOAP \(SAP RM\) Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now select None as authentication method.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:112" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

OData sender adapter is now read-only.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

With this release, OData sender adapter is not available for editing in the integration flow. It is prepopulated with data you have provided when binding OData objects to a data source.



</td>
<td valign="top">

[Editing an Integration Flow](../Development/editing-an-integration-flow-ccd062a.md) 

 <?sap-ot O2O class="- topic/xref " href="ff4cfc53ea5c440da78fe039d85b8319.xml" text="" desc="" xtrc="xref:114" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Managing unused bindings



</td>
<td valign="top">

New



</td>
<td valign="top">

SAP Cloud Integration now gives you the ability to reconfigure or delete unused bindings.



</td>
<td valign="top">

[Managing Unused Bindings](../Development/managing-unused-bindings-585639c.md) 



</td>
</tr>
<tr>
<td valign="top">

Support for $expand



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use $expand as a system query option when calling an OData API developed in SAP Cloud Integration.



</td>
<td valign="top">

[Developing an OData API Project](../Development/developing-an-odata-api-project-d961654.md) 



</td>
</tr>
</table>

**SAP Cloud Integration API**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

OData API released for customers.



</td>
<td valign="top">

New



</td>
<td valign="top">

An Open Data Protocol \(OData\) application programming interface \(API\) has been released for customers that allows you to access data \(for example, monitoring data\).



</td>
<td valign="top">

[OData API](../Development/odata-api-a617d6f.md) 



</td>
</tr>
</table>

These release notes correspond to the customer shipment on **2016-07-16**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.19.\***

Node Assembly \(Cluster 1.x\): **1.38.\***

Node Assembly \(Cluster 2.x\): **2.16.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Use Temporary File



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the*Use Temporary File* function to write the data to a temporary file initially. Once the write procedure is finished, the temp file is renamed to the target file.



</td>
<td valign="top">

[Configure the SFTP Receiver Adapter](../Development/configure-the-sftp-receiver-adapter-4ef52cf.md)



</td>
</tr>
<tr>
<td valign="top">

Monitoring application user interface changed



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In the Integration Content Monitor the data is presented slightly different than before.



</td>
<td valign="top">

[Manage Integration Content](../Operations/manage-integration-content-09a7223.md) 



</td>
</tr>
<tr>
<td valign="top">

Done File Expected



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the new Read Lock Strategy *Done File Expected*to signal that the file to be processed is ready for consumption.



</td>
<td valign="top">

[Configure the SFTP Sender Adapter](../Development/configure-the-sftp-sender-adapter-2de9ee5.md)



</td>
</tr>
<tr>
<td valign="top">

Partner content



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now access and use integration content from partners in the public catalog.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="ad1d6124df8540259302a8787e79217c.xml" text="" desc="" xtrc="xref:132" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Timeout option for SuccessFactors adapter with SOAP message protocol



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now configure timeout or the maximum time the adapter waits for a response in the SuccessFactors adapter with SOAP message protocol.



</td>
<td valign="top">

[SuccessFactors SOAP Adapter](../Development/successfactors-soap-adapter-28b29d6.md)



</td>
</tr>
<tr>
<td valign="top">

Create\(POST\) operation available for SuccessFactors adapter with OData V4 message protocol in the receiver channel



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use Create\(POST\) operation with SuccessFactors adapter with OData V4 message protocol in the receiver channel.



</td>
<td valign="top">

[SuccessFactors OData V4 Receiver Adapter](../Development/successfactors-odata-v4-receiver-adapter-cd091fc.md)



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Use Temporary File



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the*Use Temporary File* function to write the data to a temporary file initially. Once the write procedure is finished, the temp file is renamed to the target file.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a9d84ab623bc436db8ddd073db6b5165.xml" text="" desc="" xtrc="xref:135" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Decoder - MIME Multipart



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

When *Add Multipart Header Inline* is selected and the inbound message is, other than expected, no MIME multipart message with inline headers, the resulting message is identical to the original one. Using the previous software version, an empty message was returned instead.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="10d649ed16db446183f466d15dba199e.xml" text="" desc="" xtrc="xref:136" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Done File Expected



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the new Read Lock Strategy *Done File Expected*to signal that the file to be processed is ready for consumption.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="6199b175528740d88cb6d07e621275b9.xml" text="" desc="" xtrc="xref:137" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Create\(POST\) operation available for SuccessFactors adapter with OData V4 message protocol in the receiver channel



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now use Create\(POST\) operation with SuccessFactors adapter with OData V4 message protocol in the receiver channel.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9c915cc929d84559997c12e18c74e9f0.xml" text="" desc="" xtrc="xref:138" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Timeout option for SuccessFactors adapter with SOAP message protocol



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now configure timeout or the maximum time the adapter waits for a response in the SuccessFactors adapter with SOAP message protocol.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="aad94bc587904765b64f1bbbf80aac19.xml" text="" desc="" xtrc="xref:139" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
</table>

No new features or releases for **Integration Operations \(Eclipse\), and Service Development**.



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_lgc_cxw_rdb"/>

## 04 June 2016

These release notes correspond to the customer shipment on **2016-06-04**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.18.\***

Node Assembly \(Cluster 1.x\): **1.37.\***

Node Assembly \(Cluster 2.x\): **2.15.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Maximum number of iterations increased for looping process call



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The maximum number of iterations for the looping process call has been increased to 9999.



</td>
<td valign="top">

[Define Looping Process Call](../Development/define-looping-process-call-f58c2ba.md) 



</td>
</tr>
<tr>
<td valign="top">

SFTP receiver adapter can handle temporary files



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now configure a temporary file name for the *Override* option of the SFTP receiver adapter in order to make sure that only completely written files are being processed subsequently.



</td>
<td valign="top">

[Configure the SFTP Receiver Adapter](../Development/configure-the-sftp-receiver-adapter-4ef52cf.md) 



</td>
</tr>
<tr>
<td valign="top">

Web UI Monitoring - certificate-to-user mapping capabilities enhanced



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can map multiple certificates to the same user \(n:1 certificate-to-user mappings are now possible\).



</td>
<td valign="top">

[Authentication and Authorization Options \(Inbound\)](../ConnectionSetup/authentication-and-authorization-options-inbound-983f2a5.md)

[Client Certificate Authentication and Certificate-to-User Mapping \(Inbound\), Neo Environment](../ConnectionSetup/client-certificate-authentication-and-certificate-to-user-mapping-inbound-neo-environment-4b5afdd.md)



</td>
</tr>
<tr>
<td valign="top">

Web UI Monitoring - Managing Integration Content



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You cannot download configure-only content any more.



</td>
<td valign="top">

[Manage Integration Content](../Operations/manage-integration-content-09a7223.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Maximum number of iterations increased for looping process call



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The maximum number of iterations for the looping process call has been increased to 9999.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="bcb885971519439790aafb61ad6c5474.xml" text="" desc="" xtrc="xref:156" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

New externalizable parameters for SFTP sender adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Certain Post Processing parameters are now externalizable.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="1db65d7205864e638627265ee7f32bf0.xml" text="" desc="" xtrc="xref:157" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

SFTP receiver adapter can handle temporary files



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now configure a temporary file name for the *Override* option of the SFTP receiver adapter in order to make sure that only completely written files are being processed subsequently.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a9d84ab623bc436db8ddd073db6b5165.xml" text="" desc="" xtrc="xref:158" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Integration Operations - Deployed Artifacts



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You cannot download configure-only content any more.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="8a43e29496154ebe8683bf9e4178a108.xml" text="" desc="" xtrc="xref:159" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

New externalizable parameter for IDoc \(IDoc-SOAP\), SOAP \(SAP RM\) and SOAP \(SOAP 1.x\) receiver adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can externalize the*Allow Chunking* parameter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="1db65d7205864e638627265ee7f32bf0.xml" text="" desc="" xtrc="xref:161" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

AS2 Adapter - new retry handling



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The AS2 adapter will no longer generate an additional message processing log \(MPL\) for the initial message reception process. This information is now merged into the MPL which is regularly created for the integration flow starting with the AS2 channel.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a5eebca5329749669660b1779202b4c0.xml" text="" desc="" xtrc="xref:162" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Developing OData APIs in Beta



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

This feature is now in beta version.



</td>
<td valign="top">

[Developing an OData API Project](../Development/developing-an-odata-api-project-d961654.md) 



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_xpd_cxw_rdb"/>

## 07 May 2016

These release notes correspond to the customer shipment on **2016-05-07**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.17.\***

Node Assembly \(Cluster 1.x\): **1.36.\***

Node Assembly \(Cluster 2.x\): **2.14.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/mars/](https://tools.hana.ondemand.com/mars/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

HTTP receiver adapter: dynamic configuration of *Credential Name* 



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically configure the *Credential Name*property \(when basic authentication is specified\) by entering either a header or a parameter name.



</td>
<td valign="top">

[HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md) 



</td>
</tr>
<tr>
<td valign="top">

Web-based Monitoring - new message processing log property added



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The *CorrelationId* was added that allows you to identify correlated messages.



</td>
<td valign="top">

[Monitor Message Processing](../Operations/monitor-message-processing-314df3f.md) 



</td>
</tr>
<tr>
<td valign="top">

SFTP adapter enhanced by new capabilities



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The SFTP adapter has been enhanced by the following new capabilities:

-   SFTP sender and receiver adapter: For the connection to the SFTP server, authentication based on user name and password \(defined by a *User Credential* artifact\) has been enabled. Before, only authentication based on a public key was possible.

-   SFTP sender adapter: New version of *Scheduler* tab is available.

-   SFTP sender adapter: As *File Name*, you can now enter file name patterns \(using `*` and `?` character\).




</td>
<td valign="top">

[Configure the SFTP Sender Adapter](../Development/configure-the-sftp-sender-adapter-2de9ee5.md)

[Configure the SFTP Receiver Adapter](../Development/configure-the-sftp-receiver-adapter-4ef52cf.md)



</td>
</tr>
<tr>
<td valign="top">

Retry handling in JMS adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

**One message processing log \(MPL\)** will be generated for each involved **integration flow** which is connected to the JMS queue.



</td>
<td valign="top">

[JMS Adapter](../Development/jms-adapter-0993f2a.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Eclipse Mars now supported



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The Integration Designer and the Integration Operations feature now run on Eclipse Mars edition.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="4ba9fa6f288446bb98be3aede3b66b80.xml" text="" desc="" xtrc="xref:180" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

HTTP receiver adapter: dynamic configuration of *Credential Name* 



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically configure the *Credential Name*property \(when basic authentication is specified\) by entering either a header or a parameter name.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:181" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

MIME multipart encoder stephas been enhanced.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically add headers in the MIME multipart encoder step.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

SFTP adapter enhanced by new capabilities



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The SFTP adapter has been enhanced by the following new capabilities:

-   SFTP sender and receiver adapter: For the connection to the SFTP server, authentication based on user name and password \(defined by a *User Credential* artifact\) has been enabled. Before, only authentication based on a public key was possible.

-   SFTP sender adapter: New version of Scheduler tab is available.

-   SFTP sender adapter: As *File Name*, you can now enter file name patterns \(using `*` and `?` character\).




</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="6199b175528740d88cb6d07e621275b9.xml" text="" desc="" xtrc="xref:182" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="a9d84ab623bc436db8ddd073db6b5165.xml" text="" desc="" xtrc="xref:183" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Retry handling in JMS adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

**One message processing log \(MPL\)** will be generated for each involved **integration flow** which is connected to the JMS queue.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="18cb520cf8e74c528b14312058e8e38e.xml" text="" desc="" xtrc="xref:185" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Eclipse Mars now supported



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The Integration Designer and the Integration Operations feature now run on Eclipse Mars edition.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="4ba9fa6f288446bb98be3aede3b66b80.xml" text="" desc="" xtrc="xref:186" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Message Monitoring - new message processing log property added



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The *CorrelationId* was added that allows you to identify correlated messages.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="ce3fcff9b07941269ea0e41908dfda3f.xml" text="" desc="" xtrc="xref:187" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_jff_cxw_rdb"/>

## 09 April 2016

These release notes correspond to the customer shipment on **2016-04-09**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.16.\***

Node Assembly \(Cluster 1.x\): **1.35.\***

Node Assembly \(Cluster 2.x\): **2.13.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Configure OData adapter assigned to sender channel



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now assign an OData adapter to the sender channel in an integration project and configure it.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="ff4cfc53ea5c440da78fe039d85b8319.xml" text="" desc="" xtrc="xref:197" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Looping process call in Web UI



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now define a looping process call in the Web UI.



</td>
<td valign="top">

[Define Looping Process Call](../Development/define-looping-process-call-f58c2ba.md) 



</td>
</tr>
<tr>
<td valign="top">

New product profile



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

A new product profille *SAP Process Orchestration 7.5 SP3* can now be activated under *Settings* \(when your tenant is configured accordingly by SAP\).



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Define an Encoder



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now find more information about the encoding scheme MIME multipart in the Encoder/Decoder documentation



</td>
<td valign="top">

[Define an Encoder](../Development/define-an-encoder-89f8bdd.md)

[Define a Decoder](../Development/define-a-decoder-c95697a.md)



</td>
</tr>
<tr>
<td valign="top">

Support for OData V4 message protocol in SuccessFactors Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now access SuccessFactors OData V4 service using the SuccessFactors adapter.



</td>
<td valign="top">

[SuccessFactors OData V4 Receiver Adapter](../Development/successfactors-odata-v4-receiver-adapter-cd091fc.md) 



</td>
</tr>
<tr>
<td valign="top">

Configure B2B Integration



</td>
<td valign="top">

New



</td>
<td valign="top">

The configure B2B integration area provides an overview of number ranges related artifacts.



</td>
<td valign="top">

[Managing Number Ranges](../Operations/managing-number-ranges-b6e17fa.md) 



</td>
</tr>
</table>

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Configure OData adapter assigned to sender channel



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now assign an OData adapter to the sender channel in an integration project and configure it.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3b52ea0b3973478094931f399f6c5696.xml" text="" desc="" xtrc="xref:203" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Support for OData V4 message protocol in SuccessFactors Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now access SuccessFactors OData V4 service using the SuccessFactors adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9c915cc929d84559997c12e18c74e9f0.xml" text="" desc="" xtrc="xref:204" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
</table>

**Service Development**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Developing OData APIs



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now develop and provision OData APIs from existing data sources such as SOAP, REST and OData.



</td>
<td valign="top">

[Developing an OData API Project](../Development/developing-an-odata-api-project-d961654.md) 



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_lpg_cxw_rdb"/>

## 12 March 2016

These release notes correspond to the customer shipment on **2016-03-12**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.15.\***

Node Assembly \(Cluster 1.x\): **1.34.\***

Node Assembly \(Cluster 2.x\): **2.12.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Web-based Monitoring UI changed



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

the user interface of the *Monitor Message Processing* editor has been changed \(master-detail view enhanced\).



</td>
<td valign="top">

[Monitor Message Processing](../Operations/monitor-message-processing-314df3f.md) 



</td>
</tr>
<tr>
<td valign="top">

Dynamic Parameters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can find a list of parameters that can be set dynamically at runtime.



</td>
<td valign="top">

[Dynamic Parameters \(Example\)](../Development/dynamic-parameters-example-5705f2b.md) 



</td>
</tr>
</table>

No new features or releases for **SAP Integration Advisor**.

**Integration Designer \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Dynamic Parameters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can find a list of parameters that can be set dynamically at runtime.



</td>
<td valign="top">

[Dynamic Parameters \(Example\)](../Development/dynamic-parameters-example-5705f2b.md) 



</td>
</tr>
<tr>
<td valign="top">

Externalizing Parameters of Integration Flow



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can find a list of parameters that can be externalized.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="1db65d7205864e638627265ee7f32bf0.xml" text="" desc="" xtrc="xref:222" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

**Integration Operations \(Eclipse\)**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Properties view for nodes: new property Profile for nodes



</td>
<td valign="top">

New



</td>
<td valign="top">

A new property *Profile* is displayed for nodes in the Properties view.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="ab9f8bfa719f469cac12dd5c8da27f73.xml" text="" desc="" xtrc="xref:225" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>



<a name="loio2f5d4f15e3944e7d86109406afbaf054__section_sd3_cxw_rdb"/>

## 13 February 2016

These release notes correspond to the customer shipment on **2016-02-13**.

These release notes correspond to the following released software versions:

**Software Version**

Tooling: **2.14.\***

Node Assembly \(Cluster 1.x\): **1.33.\***

Node Assembly \(Cluster 2.x\): **2.11.\***

> ### Note:  
> To check if you have this node assembly version, open the *Integration Operations* perspective in Eclipse, and in the Node Explorer, position the cursor on the tenant name. The node assembly version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including Streaming

For scenarios that include streaming data is written to the file system when the data volume exceeds a specific threshold value. The files are encrypted. The encryption algorithm has been changed from RC4 to AES/CTR/NoPadding, and the threshold has been increased from 64/128 KB to 1 MB.

The new values are used for new or redeployed integration flows. Already deployed integration flows will still use the old values. Therefore, you need to redeploy the integration flows if the new values are to be used for existing integration flows.



### Features

**Web UI**


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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Web UI Monitoring: changes in Message Monitor



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Web UI Monitoring: *Integration Flow Name* was renamed to *Artifact Name* \(to other artifact types support future\). Attribute *Artifact Type* has been added.



</td>
<td valign="top">

[Monitor Message Processing](../Operations/monitor-message-processing-314df3f.md) 



</td>
</tr>
<tr>
<td valign="top">

Web UI Monitoring: changes in Integration Content Monitor



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Web UI Monitoring shows under *Managing Integration Content* \(in the attribute details section\) the field *Deploy State* was renamed to *State* and provides the state of the artefact with regard to configure-only content.



</td>
<td valign="top">

[Manage Integration Content](../Operations/manage-integration-content-09a7223.md) 



</td>
</tr>
<tr>
<td valign="top">

Auto-update of Integration Packages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Integration packages get auto-updated once the date of manually updating them expires.



</td>
<td valign="top">

[Add Integration Packages to the Customer Workspace](../Development/add-integration-packages-to-the-customer-workspace-ae1b98a.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring: Managing certificate-to-user mappings



</td>
<td valign="top">

New



</td>
<td valign="top">

A new combination of authentication and authorization for inbound messages is supported \(for HTTPS connections\). A new artifact \(*Certificate-to-User Mapping*\) has been introduced for that purpose that can be managed in the *Monitoring* section of the Web application.

Using a certificate-to-user mapping, a user can be authenticated based on a certificate. Certificate-to-user mappings make sure that a user is always associated with the certificate as a whole, not only with one attribute of it \(for example the common name \(CN\)\).



</td>
<td valign="top">

[Managing Certificate-to-User Mappings, Neo Environment](../Operations/managing-certificate-to-user-mappings-neo-environment-88ea2e5.md)

[Client Certificate Authentication and Certificate-to-User Mapping \(Inbound\), Neo Environment](../ConnectionSetup/client-certificate-authentication-and-certificate-to-user-mapping-inbound-neo-environment-4b5afdd.md)



</td>
</tr>
<tr>
<td valign="top">

Adding additional header field to message using the Content Modifier or Script step



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can add an additional header \(`SAP_MessageType`\) to a message using the Content Modifier or Script step. This header will also be dispalyed in the message processing log.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3983143d6f8f4ea49461d4f167b5ae6f.xml" text="" desc="" xtrc="xref:243" xtrf="file:/home/builder/src/dita-all/cdo1688560638547/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2f5d4f15e3944e7d86109406afbaf054.xml" ?>  



</td>
</tr>
</table>

