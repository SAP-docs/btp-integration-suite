<!-- loiof3b13e456c6544cd97232275bd3c2288 -->

# 2017 SAP Cloud Integration \(Archive\)



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_wpb_cmz_qbb"/>

## 09 December 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.38.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.35.\*



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

RFC receiver adapter now supports auto commit feature for BAPI functions that require BAPI\_TRANSACTION\_COMMIT to be invoked implicitly by the RFC.

For more information, see:

-   [RFC Receiver Adapter](../Development/rfc-receiver-adapter-5c76048.md)

-    <?sap-ot O2O class="- topic/xref " href="b61dbaedd4244b10b04f1be1d68c0e40.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

The integration flow editor available in Web application has a new improved interface that helps the integration developers to work efficiently.

For more information, see [Configure Integration Flow Components](../Development/configure-integration-flow-components-3171795.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

You can now upload a single or multiple resources either from the file system or integration flow that is within the tenant.

For more information, see [Manage Resources of an Integration Flow](../Development/manage-resources-of-an-integration-flow-b5968b2.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application.

The keystore management feature facilitates the renewal of SAP keys.

You can now activate a new key pair provided by SAP in order to replace an old key pair which is supposed to expire soon. To access new SAP keys \(provided by SAP\), a new*New SAP Keys* section has been added to the keystore management feature.

A new *SAP Key History* section shows expired SAP keys which have been replaced by new ones. You can also restore a key pair from the *SAP Key History*.

For more information, see:

[Managing the Lifecycle of Keys](../Operations/managing-the-lifecycle-of-keys-7d24b61.md)

[Activating a New Key Pair Provided by SAP](../Operations/activating-a-new-key-pair-provided-by-sap-383be7a.md)

[Restoring a Key Pair from the Key History](../Operations/restoring-a-key-pair-from-the-key-history-43965e7.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application.

You can view all parameters of the component using *For expired keys, the end of validity period is highlighted inAll Parameters* option, when you configure externalized parameters of an integration flow.

More information:

[Configure Externalized Parameters of an Integration Flow](../Development/configure-externalized-parameters-of-an-integration-flow-462a478.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

This feature is available in Web application.

New features are introduced through new versions of the components. To consume this new feature you must migrate to new version.

More information:

[Migrate an Integration Flow Component to a New Version](../Development/migrate-an-integration-flow-component-to-a-new-version-61bf6a2.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application and in Eclipse.

In the JMS Receiver Adapter you can select this option to also transfer the exchange properties to the JMS queue.

For more information, see:

[JMS Adapter](../Development/jms-adapter-0993f2a.md)

 <?sap-ot O2O class="- topic/xref " href="18cb520cf8e74c528b14312058e8e38e.xml" text="" desc="" xtrc="xref:13" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application.

With the new status *Blocked* in the Message Queue Monitor you can now see which messages were involved in multiple node crashes and were therefore not processed.

For more information, see:

-   [Managing Message Queues](../Operations/managing-message-queues-cdcce24.md)




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

The list of subprocessors for SAP BTP has been updated and a new version is available on SAP Support Portal:

[SAP Subprocessors](https://support.sap.com/en/my-support/subprocessors.html)

Please find the direct link to the updated list at: [Subprocessor List](https://support.sap.com/content/dam/support/en_us/library/ssp/my-support/subprocessors/SAP-Cloud-Platform-Subprocessor-List.pdf)

The following changes have been made compared to the previous version:

-   All SAP Affiliates subprocessors have been added to the list now.

-   Scale Focus AD has been added to the list of non SAP Affiliates subprocessors.


A subprocessor is any entity or individual, which has or potentially will have access to or process personal data \(as defined in applicable data protection laws\).

Note that services of SAP BTP such as, for example, Neo, are covered by this document.



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_tgj_cqc_nbb"/>

## 11 November 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.37.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.56.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.34.\*



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application.

You can display the properties of a selected keystore entry.

For more information, see:

[Displaying Properties of a Keystore Entry](../Operations/displaying-properties-of-a-keystore-entry-24585ba.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

RFC receiver adapter now supports creation of dynamic destination by using headers.

For more information, see:

-   [RFC Receiver Adapter](../Development/rfc-receiver-adapter-5c76048.md)

-    <?sap-ot O2O class="- topic/xref " href="b61dbaedd4244b10b04f1be1d68c0e40.xml" text="" desc="" xtrc="xref:21" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 




</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_pvh_5pn_1bb"/>

## 14 October 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.36.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.55.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.33.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application and in Eclipse.

The Scheduler of SFTP and Mail sender adapter has been changed so that the option *Run Once* has been removed. Furthermore, default values for the interval under *Schedule on Day* and *Schedule to Recur* have been changed so that the scheduler runs by default every 10 seconds between 00:00 and 24:00 o'clock.

For more information, see:

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:22" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="6199b175528740d88cb6d07e621275b9.xml" text="" desc="" xtrc="xref:23" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

[Mail Adapter](../Development/mail-adapter-f1145cc.md)

[Configure the SFTP Sender Adapter](../Development/configure-the-sftp-sender-adapter-2de9ee5.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

This feature is available in Web application and in Eclipse.

In the WS Security settings, you can now specify a signature algorithm to be applied when signing the response message.

For more information, see:

 <?sap-ot O2O class="- topic/xref " href="efff064fdb9140adbc4e195fdf906e3e.xml" text="" desc="" xtrc="xref:26" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:27" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

This feature is available in Web application.

You can now import or add different file types to an integration content.

For more information, see [Manage Resources of an Integration Flow](../Development/manage-resources-of-an-integration-flow-b5968b2.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

You now access the User Credential and Key Store in SAP ADK project to authenticate and validate a user.

For more information, see:

-   [Accessing Trust and Key Managers](../Development/accessing-trust-and-key-managers-8518837.md)

-   [Accessing User Credentials](../Development/accessing-user-credentials-e4e4edc.md)




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

This feature is available in Web application.

In the Message Queue Monitor you can now display the integration flows in which a queue is used and show unused and missing queues.

For more information, see [Managing Message Queues](../Operations/managing-message-queues-cdcce24.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

EDIFACT syntax version 4 is now supported.

For more information, see [Define EDI Splitter](../Development/define-edi-splitter-584a3be.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

RFC receiver adapter version 1.2.0 and higher supports:

-   function modules that contain "/" in their names
-   table in import parameter

For more information, see:

 <?sap-ot O2O class="- topic/xref " href="b61dbaedd4244b10b04f1be1d68c0e40.xml" text="" desc="" xtrc="xref:33" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

[RFC Receiver Adapter](../Development/rfc-receiver-adapter-5c76048.md)



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_yqf_3xg_v1b"/>

## 16 September 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.35.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.54.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.32.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhancement

This feature is available in Web application.

You can now view externalised values by selecting relevant details of externalised components in*More* tab.

More information: [Configure Externalized Parameters of an Integration Flow](../Development/configure-externalized-parameters-of-an-integration-flow-462a478.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

You can now transport integration content using *Change and Transport System \(CTS+\)* tool.

For more information, see [Content Transport](../Development/content-transport-e3c79d6.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

Now you can include additional properties in the URI, for retrieving specific information on an custom adapter \(SAP ADK\) during runtime.

For more information, see [Develop Adapters](../Development/develop-adapters-f798db6.md).



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_ttd_zds_k1b"/>

## 19 August 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.34.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.53.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.31.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The following feature is available in Web UI in Cloud Integration.

You can now back up and restore keystore entries which are owned by the tenant administrator.

More information:

[Backing Up Keystore Entries](../Operations/backing-up-keystore-entries-b8e03b7.md)

[Restoring Backed-Up Keystore Entries](../Operations/restoring-backed-up-keystore-entries-bfbbf91.md)



</td>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

You can now use content assist feature for groovy script which means that you can view list of existing methods of message class, once you start typing initial letters of the required method. You can add content assist jar file in integration project to use this feature.

For more information, see  <?sap-ot O2O class="- topic/xref " href="905b24171cc746ef9069939ff3b536db.xml" text="" desc="" xtrc="xref:45" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The *Credential Name* attribute can now be configured dynamically in the IDoc, SOAP SOAP 1.x and SOAP SAP RM receiver adapters.

This feature is available in the Web UI and in Eclipse.

For more information, see \(for the Web UI\):

 <?sap-ot O2O class="- topic/xref " href="9597227a3a044904988fb9dca54aaceb.xml" text="" desc="" xtrc="xref:46" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?>  

 <?sap-ot O2O class="- topic/xref " href="efff064fdb9140adbc4e195fdf906e3e.xml" text="" desc="" xtrc="xref:47" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

[SOAP \(SAP RM\) Adapter](../Development/soap-sap-rm-adapter-6bd724f.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The Partner Directory has been released for SAP Cloud Integration product profile.

The Partner Directory contains information on partners that are connected to a cross-partner tenant in the context of a larger network

You can use the Partner Directory when setting up a network of many communication partners. Partner-specific information can be parameterized in a few integration flows \(which dynamically read the partner-specific information from the Partner Directory\). That way, you can easily add new partners to the network without changing or redeploying integration flows.



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse or Web UI in Cloud Integration.

Cloud Connector Proxy in Mail Sender Adapter is supported.

For more information, see

-    <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:49" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-   [Mail Adapter](../Development/mail-adapter-f1145cc.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

As of this tact, SOAP \(SAP RM adapter\) can also be used in combination with the Send step type.

This feature is available in the Web UI and in Eclipse.

For more information, see

 <?sap-ot O2O class="- topic/xref " href="b068577a9c564d69a9f63f11fe0372f5.xml" text="" desc="" xtrc="xref:51" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

[Define a Send Step](../Development/define-a-send-step-9b83f10.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The **Dead-letter** queue option has been introduced in AS2 adapter. This option enables you to place those messages that cannot be processed after two retries.

-   For more information, see  <?sap-ot O2O class="- topic/xref " href="63a96540c8494b578ec657bdfa5be6b8.xml" text="" desc="" xtrc="xref:53" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .

-   For more information, see  <?sap-ot O2O class="- topic/xref " href="a5eebca5329749669660b1779202b4c0.xml" text="" desc="" xtrc="xref:54" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

SAP ADK framework has introduced a new adapter project creation wizard with maven plugin support. It allows you to build and deploy custom adapters.

For more information, see [Develop Adapters](../Development/develop-adapters-f798db6.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The authentication option has been enhanced in POP3 Connectivity Test, IMAP Coonectivity Test and SMTP Connectivity Test.

For more information, see

[Performing Connectivity Tests](../Operations/performing-connectivity-tests-d5b2fae.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The usability of the Manage Locks, the Manage Queues and the Manage Keystore areas of the MonitorWeb UI has been improved.

The content of the *Entry* property provides a link to the message in the *Managing Message Queues* monitor.

A filter and a quick search field has been introduced.

For more information, see

[Message Locks](../Operations/message-locks-bce9ae0.md)

[Managing Message Queues](../Operations/managing-message-queues-cdcce24.md)

[Managing Keystore Entries](../Operations/managing-keystore-entries-2dc8942.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

You can now disable a field in the target structure in a mapping definition resource. This helps you in testing or simulating the mapping without mapping the mandatory fields.

For more information, see <?sap-ot O2O class="- topic/xref " href="3f2f4bb739b84bf48154d6734869a992.xml" text="" desc="" xtrc="xref:60" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

Operational Aspects: List of subprocessors \(non SAP affiliates\) for SAP BTP updated

The list of subprocessors \(non SAP affiliates\) for SAP BTP has been updated. A subprocessor is any entity or individual, which has or potentially will have access to or process personal data \(as defined in applicable data protection laws\).

Note that services of SAP BTP such as, for example, SAP Cloud Integration, are covered by this document.

The following subprocessors have been added:

Accenture GmbH

Dynatrace GmbH

Kaavian Systems

Find the updated list at: [Subprocessor \(non SAP Affiliates\) List](https://support.sap.com/content/dam/support/en_us/library/ssp/my-support/subprocessors/SAP%20Cloud%20Platform%20Subprocessor%20(non%20SAP%20Affiliates)%20List.pdf)



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_olm_znw_b1b"/>

## 21 July 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.33.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.52.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.30.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

RFC Receiver Adapter is generally available now and can be used from Eclipse or Web UI in Cloud Integration.

RFC is the standard interface used for integrating On-premise ABAP systems to the systems hosted on cloud using SAP Cloud Connector. The adapter supports NetWeaver 7.31 version or higher.

For more information, see

-    <?sap-ot O2O class="- topic/xref " href="b61dbaedd4244b10b04f1be1d68c0e40.xml" text="" desc="" xtrc="xref:62" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-   [RFC Receiver Adapter](../Development/rfc-receiver-adapter-5c76048.md)




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

Logging can be implemented by using Simple Logging Facade for Java \(SLF4J\).

For more information, see [Develop Adapters](../Development/develop-adapters-f798db6.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

Developing an OData API is generally available now. This service was previously in beta version.



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse or Web UI in Cloud Integration.

Cloud Connector Proxy in Mail Receiver Adapter is supported. You can now use the Mail Receiver Adapter to send emails via the SAP Cloud Connector to the receiver.

For more information, see

-    <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:65" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-   [Mail Adapter](../Development/mail-adapter-f1145cc.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhancement

You can now configure the script in the custom function to return multiple string values.

For more information, see <?sap-ot O2O class="- topic/xref " href="376a16ca0d0a4ebeb78fe3d7af333d79.xml" text="" desc="" xtrc="xref:67" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse or Web UI in Cloud Integration.

You can now place messages in the dead-letter queue if it cannot be processed after two retries.

For more information, see

-    <?sap-ot O2O class="- topic/xref " href="18cb520cf8e74c528b14312058e8e38e.xml" text="" desc="" xtrc="xref:68" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 
-   [JMS Adapter](../Development/jms-adapter-0993f2a.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse or Web UI in Cloud Integration.

You can now configure HTTP Session Handling in the Runtime Configuration.

For more information, see

-    <?sap-ot O2O class="- topic/xref " href="c5eeddd36c0143c18258e5f9210803e9.xml" text="" desc="" xtrc="xref:70" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 
-   [Specify the Runtime Configuration](../Development/specify-the-runtime-configuration-0c1c96e.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The SAP Cloud Integration, enterprise edition supports additional capabilities of an integration flow.

More information: [Licensed Capabilities and Features](../WhatIsCloudIntegration/licensed-capabilities-and-features-cd0b75e.md) 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

Keystore management in the Web UI has been enhanced in the following way:

The tenant administrator can now also download SSH keystore entries for SFTP connections \(with alias `id_rsa` or `id_dsa`\) in OpenSSH format.

More information: [Downloading Single Keystore Entries](../Operations/downloading-single-keystore-entries-ca8a663.md) 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

Authentication via principal propagation is now available in the OData adapter.

For more information, see  <?sap-ot O2O class="- topic/xref " href="ff4cfc53ea5c440da78fe039d85b8319.xml" text="" desc="" xtrc="xref:76" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

Message Monitoring/Managing Locks allows you to deal with messages that cannot be processed and are placed in the dead-letter queue.

More information: [Message Locks](../Operations/message-locks-bce9ae0.md)



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_orl_ft3_zz"/>

## 24 June 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.32.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.51.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.29.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

A new Keystore Monitor in the Web UI allows the tenant administrator to display entries of the tenant keystore and to manage those entries which are owned by the tenant administrator.

The Keystore Monitor provides you with an overview of the entries of the keystore \(deployed on the tenant\).

Furthermore, the Keystore Monitor provides you with the following options:

-   Uploading a keystore

-   Downloading the public content of a keystore or a single keystore entry

-   Deleting a keystore entry


For more information, see [Managing Keystore Entries](../Operations/managing-keystore-entries-2dc8942.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

Externalize feature is now available in the Web UI of Cloud Integration. It allows you to declare a parameter as a variable and reuse the same variable in more than one integration component.

For more information, see [Externalize Parameters of an Integration Flow](../Development/externalize-parameters-of-an-integration-flow-45b2a07.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The Resources viewer in the Web UI of Cloud Integration helps you to manage different resources associated within an integration content.

For more information, see [Manage Resources of an Integration Flow](../Development/manage-resources-of-an-integration-flow-b5968b2.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

Now you can introduce custom classes using Blueprint metadata during runtime for custom adapters.

For more information, see:

[Develop Adapters](../Development/develop-adapters-f798db6.md).

[Blueprint Metadata](../Development/blueprint-metadata-ab38cc8.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The OData API was enhanced to support keystore management activities by the tenant administrator.

For more information, see  <?sap-ot O2O class="- topic/xref " href="9c26ac71c5a54e65a7550aacd58ca1b1.xml" text="" desc="" xtrc="xref:85" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The OData API allows you to address certificate-to-user mappings.

For more information, see  <?sap-ot O2O class="- topic/xref " href="3e3d82939da64fb898539421cd0e9a02.xml" text="" desc="" xtrc="xref:86" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

Provisioning message broker allows you \(tenant admin\) to use JMS adapter scenarios only if you have *Enterprise Edition* license.

For more information, see [Activating Enterprise Messaging](../Operations/activating-enterprise-messaging-a74cddc.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

JMS Adapter and Message Queue Monitor is available for Cloud Integration Customer only if you have *Enterprise Edition* license.

For more information, see  <?sap-ot O2O class="- topic/xref " href="18cb520cf8e74c528b14312058e8e38e.xml" text="" desc="" xtrc="xref:88" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

The Web UI now supports also an additional transaction handling configuration option *Required for JMS*.

For more information, see [Define Transaction Handling](../Development/define-transaction-handling-2a5d4bc.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

New

Parameter *CRAM-MD5* in Sender/Receiver Mail Adapter was renamed to *Encrypted User/Password*

For more information, see  <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:90" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

Enhanced

Operational Aspects: List of subprocessors \(non SAP affiliates\) updated

The list of subprocessors \(non SAP affiliates\) has been updated. A subprocessor is any entity or individual, which has or potentially will have access to or process personal data \(as defined in applicable data protection laws\).

Note that services such as, for example, SAP Cloud Integration, are covered by this document.

Find the updated list at: [List of Subprocessors \(non SAP Affiliates\)](https://support.sap.com/content/dam/support/en_us/library/ssp/my-support/subprocessors/SAP%20Cloud%20Platform%20Subprocessor%20%28non%20SAP%20Affiliates%29%20List%20v13%20%28002%29.pdf)



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_hjq_h3j_lz"/>

## 27 May 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.31.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.50.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.28.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

You can now create or upload value mapping artifacts to your integration package.

For more information, see [Creating Value Mapping](../Development/creating-value-mapping-25eff9b.md).



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

For methods GET, DELETE, and HEAD you can now send the body of a message with the request.

More information:

-    <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:93" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-   [HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following are the new additions included while developing an new adapter:

-   In component metadata, a new child element for FixedValue\(s\) property has been introduced.

-   In develop adapters chapter mentions the format used to construct an application URL for calling a servlet.

More information:

-   [Component Metadata](../Development/component-metadata-550b19e.md)

-   [Develop Adapters](../Development/develop-adapters-f798db6.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New** 

The following feature is available in Eclipse and in the Web UI of SAP Cloud Integration.

You can now process and route failed EDI messages using EDI splitter.

More information:

-   [Define EDI Splitter](../Development/define-edi-splitter-584a3be.md) \(Web UI\)

-    <?sap-ot O2O class="- topic/xref " href="45b45a08f75d440a853d33f3e769b70d.xml" text="" desc="" xtrc="xref:98" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?>  \(Eclipse\)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The SMTP Outbound Connection Test has been enhanced in the Eclipse tooling of Cloud Integration.

You can now download certificates, check for mail addresses and validate the server certificate.

More information:  <?sap-ot O2O class="- topic/xref " href="c834dd0512774ffab268a83bfdcc3b48.xml" text="" desc="" xtrc="xref:99" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The following feature is available in the Eclipse tooling of Cloud Integration.

The *Data Store* viewer now also downloads headers.

More information:  <?sap-ot O2O class="- topic/xref " href="2dcd5ff49449489a993479b98238e759.xml" text="" desc="" xtrc="xref:100" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced**

The *Managing Locks* editor in the Web UI of Cloud Integration has been improved and made more user-friendly. You can now filter or search for entries, for example.

More information: [Message Locks](../Operations/message-locks-bce9ae0.md)



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_rc1_bbm_fz"/>

## 29 April 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.30.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.49.0



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.27.0



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The feature *Managing Locks* is available in the Web UI of Cloud Integration.

It allows you to display and manage lock entries that are created when more than one runtime nodes try to process a file at the same time

More information: [Message Locks](../Operations/message-locks-bce9ae0.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

Cloud Integration tools are supported on Eclipse Neon only. You will get update for Cloud Integration software through this Eclipse update site:.



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhanced/Enhanced**

The OData API allows you now to access the HTTP access log files \(about authentication and authorization errors for inbound HTTP communication\).

More information:

 <?sap-ot O2O class="- topic/xref " href="cb643921a2ab4a4d8c5f7fc092120811.xml" text="" desc="" xtrc="xref:104" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="fddeb49ff9344eccb9a087cb5d55a07a.xml" text="" desc="" xtrc="xref:105" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

In the SAP SOAP 1.x Sender Adapter, you can now configure the Message Exchange Pattern manually.

More information:

-    <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:106" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-    <?sap-ot O2O class="- topic/xref " href="efff064fdb9140adbc4e195fdf906e3e.xml" text="" desc="" xtrc="xref:107" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

The SOAPAction Header can now be used as a Camel Header for the following receiver adapters:

-   SOAP 1.x

-   SAP RM

-   SOAP IDoc


More information: [Headers and Exchange Properties Provided by the Integration Framework](../Development/headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The **documentation** now contains a detailed list showing which **single roles** are required in order to perform the various tasks related to Cloud Integration.



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_e21_d15_yy"/>

## 1 April 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.29.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.48.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.26.\*



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

In the SAP SOAP 1.x Receiver Adapter, you can now clean up the adapter-specific headers after the receiver call.

More information:  <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:109" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

You can use Location ID to connect a cloud connector instance to your account.

You define the Location ID in the destination configuration on the cloud side.

More information:

-    <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:110" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 


-    <?sap-ot O2O class="- topic/xref " href="16b2960160204db8a9c6098634593f72.xml" text="" desc="" xtrc="xref:111" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 


-    <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:112" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 


-    <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:113" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhancement**

In the SOAP \(SAP RM\) Adapter the processing settings have been changed to one default setting.

The following feature has been changed in Eclipse and in the Web UI of Cloud Integration.

The default setting is identical with the setting *Robust* in former releases.

The provider invokes service synchronously and the processing errors are returned to the consumer.

More information:

-    <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:114" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-   [SOAP \(SAP RM\) Adapter](../Development/soap-sap-rm-adapter-6bd724f.md)




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in Eclipse and in the Web UI of Cloud Integration.

For the SOAP \(SOAP 1.x\) receiver adapter *Principal Propagation* is now available as an *Authentication*setting.

More information:

-    <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:116" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 

-    <?sap-ot O2O class="- topic/xref " href="efff064fdb9140adbc4e195fdf906e3e.xml" text="" desc="" xtrc="xref:117" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> 




</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

The following feature is available in the Web UI of Cloud Integration.

The *JSON to XML Conveter* is now avaiable.

More information:[Define JSON to XML Converter](../Development/define-json-to-xml-converter-5a7c0cd.md)



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

**Usability enhancements to Mapping Definition Resource Editor**

In the mapping definition resource editor of Cloud Integration WebUI, you can map two selected fields and all the fields with identical names in their corresponding sub-tree by choosing ![](images/map_all_4bf8289.png). You can delete all the definitions by choosing ![](images/clear_all_8bde6f9.png).

For more information, see  <?sap-ot O2O class="- topic/xref " href="3f2f4bb739b84bf48154d6734869a992.xml" text="" desc="" xtrc="xref:119" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/f3b13e456c6544cd97232275bd3c2288.xml" ?> .



</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**New**

**Usability enhancements to workspace \(*Design* tab page\)**



</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_lt5_dq2_sdb"/>

## 4 March 2017 - SAP Cloud Integration

**Software Version**


<table>
<tr>
<td valign="top">

Tooling



</td>
<td valign="top">

2.28.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)



</td>
<td valign="top">

1.47.\*



</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)



</td>
<td valign="top">

2.25.\*



</td>
</tr>
</table>

> ### Tip:  
> To check if you have this node assembly version in your Eclipse tooling, open the *Integration Operations* perspective in Eclipse, and in the *Node Explorer*, position the cursor on the tenant name. The node assembly version is then displayed in the tooltip.


<table>
<tr>
<td valign="top">

 



</td>
<td valign="top" colspan="2">

**Enhancement**

**New Integration Flow Steps Available in WebUI**

The following security-related steps have been made available in the Web UI.

-   XML Digital Signer

    More information: [Sign the Message Content with XML Digital Signature](../Development/sign-the-message-content-with-xml-digital-signature-9a013db.md)

-   PKCS\#7 Verifyer

    More information: [Verify the PKCS\#7/CMS Signature](../Development/verify-the-pkcs-7-cms-signature-f095dc6.md)

-   XML Verifyer

    More information: [Verify the XML Digital Signature](../Development/verify-the-xml-digital-signature-090b932.md)




</td>
</tr>
</table>



<a name="loiof3b13e456c6544cd97232275bd3c2288__section_sd3_cxw_rdb"/>

## 11 February 2017 - SAP Cloud Integration

These release notes correspond to the following released software versions:

These release notes correspond to the customer shipment on **2017-02-11**.

**Software Version**

Tooling: **2.27.\*** 

Node Assembly \(Cluster 1.x\): **1.46.\***

Node Assembly \(Cluster 2.x\): **2.24.\***

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

No new features or releases for **Web UI, Integration Designer \(Eclipse\), Integration Operations \(Eclipse\), Service Development, and SAP Cloud Integration API**.

