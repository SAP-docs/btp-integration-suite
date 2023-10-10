<!-- loio723dddb325064ffda6ae6bcca280845a -->

# 2015 SAP Cloud Integration \(Archive\)



## December 2015

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.32.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
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



</td>
</tr>
</table>

No new features or releases for **SAP Integration Advisor, Integration Designer \(Eclipse\), and Service Provisioning in SAP Cloud Integration**.

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



## 20 December 2015

These release notes correspond to the customer shipment on **2015-12-20**.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.31.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
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

Facebook adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the Facebook receiver adapter to extract information from Facebook based on certain criteria such as keywords, user data, for example.



</td>
<td valign="top">

[Facebook Receiver Adapter](../Development/facebook-receiver-adapter-3dcc408.md)



</td>
</tr>
<tr>
<td valign="top">

Monitoring/Manage Security Artifacts: deploying additional artifact types



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now deploy the following artifact types:

-   SSH Known Hosts

-   Secure Parameter




</td>
<td valign="top">

[Deploying an SSH Known Hosts Artifact](../Operations/deploying-an-ssh-known-hosts-artifact-46da324.md)

[Deploying a Secure Parameter Artifact](../Operations/deploying-a-secure-parameter-artifact-4641d6c.md)



</td>
</tr>
<tr>
<td valign="top">

Monitoring/Manage Integration Content: Only one status for integration content artifacts.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

There is **only one status** \(per node\) for integration content artifacts. Before, two different statuses have been a displayed in the integration content monitor: Deploy status \(which indicated the status of the artifact distribution on the tenant cluster\) and runtime status \(which indicated the actual heath of the artifact per node as determined by its monitor\).



</td>
<td valign="top">

[Runtime Status](../Operations/runtime-status-c14a7b1.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring: adaptation of user interface design



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The design of the pages has be adapted: Functions that relate to selected elements in the table \(for example, to *Edit* a selected table entry\) are located on top of the table. Other functions \(for example, to *Add* a new element\) are located at the bottom of the editor.



</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring/Monitor processed Messages: attachments displayed as plain text



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">



</td>
<td valign="top">

[Monitor Message Processing](../Operations/monitor-message-processing-314df3f.md) 



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

Facebook adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the Facebook receiver adapter to extract information from Facebook based on certain criteria such as keywords, user data, for example.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="7bfd312eac5d4ed08401775829c4760b.xml" text="" desc="" xtrc="xref:22" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Encoding/Decoding Messages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use the encoding/decoding scheme *MIME multipart encode/decode* to transform the message content.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="f71692a70cd24824a56ca4df0f248354.xml" text="" desc="" xtrc="xref:23" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 

 <?sap-ot O2O class="- topic/xref " href="540a1103f6d846c3b9fed632b354027a.xml" text="" desc="" xtrc="xref:24" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

XML Digital Signature



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can add an enveloped transform to a detached signature for XML Digital Signature using the header *CamelXmlSignatureTransformMethods* 



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="ac6fbbf76f2a4fb6b115911c5cd86523.xml" text="" desc="" xtrc="xref:25" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
</table>



## 21 November 2015

These release notes correspond to the customer shipment on **2015-11-21**.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.30.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
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

Delete Method in HTTP Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use the delete method in HTTP Adapter



</td>
<td valign="top">

[HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md) 



</td>
</tr>
<tr>
<td valign="top">

Monitoring



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The following new features are available:

-   Sub sections have been renamed and restructured. The following sub sections are now available: *Monitor Message Processing*, *Manage Integration Content* \(covers now integration content such as integration flows\), and *Manage Security Material* \(covers now security-related artifacts\).

-   When adding or changing a tile for the *Manage Integration Content* section, you can now also specify the artifact *Type* \(which allows you to specify if you like to display only integration flows, only value mappings, or both content types\).

-   You can now deploy *User Credentials* artifacts.




</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md) 



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

Open PGP: verification of uncompressed data packets



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For input messages to be verified using Open PGP, the Compressed Data packet is now optional \(it has been mandatory before this release\).



</td>
<td valign="top">

[How OpenPGP Works](../ConnectionSetup/how-openpgp-works-29bc188.md) 



</td>
</tr>
<tr>
<td valign="top">

Delete Method in HTTP Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use the delete method in HTTP Adapter



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:37" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



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

Information on how to avoid encoding issues



</td>
<td valign="top">

New



</td>
<td valign="top">

There is a new topic on how to avoid encoding issues.



</td>
<td valign="top">

[Avoiding Encoding Issues](../Development/avoiding-encoding-issues-3018480.md) 



</td>
</tr>
</table>



## 24 October 2015

These release notes correspond to the customer shipment on **2015-10-24**.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.29.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Redeployment of Integration Flows Might be Required in Cases Including StreamingClick on the version-dependent internal Eclipse Update Site released for the

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

Twitter Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

Click on th and onYou can use the Twitter receiver adapter to extract information from the Twitter platform based on certain criteria such as keywords, user data, for example.



</td>
<td valign="top">

[Twitter Receiver Adapter](../Development/twitter-receiver-adapter-453c174.md) 



</td>
</tr>
<tr>
<td valign="top">

Message-ID Handling Soap \(SAP RM\) Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can set the message-id manually



</td>
<td valign="top">

[SOAP \(SAP RM\) Adapter](../Development/soap-sap-rm-adapter-6bd724f.md) 



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

Twitter Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the Twitter receiver adapter to extract information from the Twitter platform based on certain criteria such as keywords, user data, for example.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="6dc953d97322434e9f2a5acdc216844d.xml" text="" desc="" xtrc="xref:48" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

New



</td>
<td valign="top">

You can set the message-id manually



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Message-ID Handling Soap \(SAP RM\) Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can set the message-id manually



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:49" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
</table>



<a name="loio723dddb325064ffda6ae6bcca280845a__section_gld_lkv_qdb"/>

## 26 and 14, September 2015

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

**Software Version \(Runtime\)**

**1.28.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

These release notes correspond to the following released software versions:

These release notes correspond to the customer shipment on **2015-09-26**.



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

For SOAP messages, an error message containing a URL \(to access message processing log\) is sent back to the sender \(when configured accordingly\)



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">



</td>
<td valign="top">

[Define Error Configuration](../Development/define-error-configuration-77d0041.md) 



</td>
</tr>
<tr>
<td valign="top">

Send step



</td>
<td valign="top">

New



</td>
<td valign="top">

You can configure a Send step to specify a service call to a receiver system for scenarios and adapters where no reply is expected.



</td>
<td valign="top">

[Define a Send Step](../Development/define-a-send-step-9b83f10.md) 



</td>
</tr>
<tr>
<td valign="top">

Web-based Monitoring user interface has been refined



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Web-based Monitoring user interface has been refined. You can now, for example, display message attachments in separate tabs.



</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md) 



</td>
</tr>
<tr>
<td valign="top">

In SOAP Adapter \(SOAP 1.x\) new parameters can be externalized



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can externalize different parameters in WS-Security configuration in SOAP Adapter \(SOAP1.x\)



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="1db65d7205864e638627265ee7f32bf0.xml" text="" desc="" xtrc="xref:59" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Add Integration Package or Integration Flow



</td>
<td valign="top">

New



</td>
<td valign="top">

You have to add the integration package or integration flow to your customer workspace. This enables you to access the artifacts in that package, configure, and deploy them.



</td>
<td valign="top">

[Add Integration Packages to the Customer Workspace](../Development/add-integration-packages-to-the-customer-workspace-ae1b98a.md) 



</td>
</tr>
<tr>
<td valign="top">

Configure Product Profile



</td>
<td valign="top">

New



</td>
<td valign="top">

The tenant admin can view and configure the product profile to mark a particular product profile as default, for the tenant. This enables you to make no more changes to the product profile.



</td>
<td valign="top">

[Set Default Runtime Profile](../IntegrationSettings/set-default-runtime-profile-efebd50.md) 



</td>
</tr>
<tr>
<td valign="top">

Define Switching Product Profile



</td>
<td valign="top">

New



</td>
<td valign="top">

You can switch product profiles if you want to build integration flows for different products on the same customer tenant.



</td>
<td valign="top">

[Configure Runtime Profile for an Integration Flow](../IntegrationSettings/configure-runtime-profile-for-an-integration-flow-65cc0bc.md) 



</td>
</tr>
<tr>
<td valign="top">

Editing Scripts of a Mapping



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now modify the script of a mapping.



</td>
<td valign="top">



</td>
</tr>
</table>

**SAP Integration Advisor**


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

SAP Integration Advisor



</td>
<td valign="top">

New



</td>
<td valign="top">

SAP Integration Advisor allows business partners to easily specify and describe business requirements of business-to-business \(B2B\) interfaces, map and test them.



</td>
<td valign="top">

[SAP Integration Advisor](../IntegrationAdvisor/sap-integration-advisor-6b9fe2d.md)



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

For SOAP messages, an error message containing a URL \(to access message processing log\) is sent back to the sender \(when configured accordingly\)



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

 



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="fb5549fb3abf4edf88606e20a73237e7.xml" text="" desc="" xtrc="xref:64" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Working with Product Profiles



</td>
<td valign="top">

New



</td>
<td valign="top">

Product profile is a collection of capabilities such as success factor adapter, splitter or datastore elements, available in the product. You can consume these capabilities at the time of designing integration flows.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="2a838ca7ebc0471ca6c23977ad4ac7d3.xml" text="" desc="" xtrc="xref:65" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Deleting Adapters



</td>
<td valign="top">

New



</td>
<td valign="top">

You delete an adapter once an adapter is no more required in the system.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Multiple key-value pairs in SFAPI Parameters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now specify multiple key value pairs in SFAPI paramters while configuring SuccesFactors adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9ffdd15d82c2479eba9f92843c97b127.xml" text="" desc="" xtrc="xref:66" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
</table>

**Software Version \(Runtime\)**

**1.27.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

These release notes correspond to the following released software versions:

These release notes correspond to the customer shipment on **2015-09-14**.

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
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

Dynamic attributes for the HTTP adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically configure the Address and Query field of the HTTP adapter.



</td>
<td valign="top">

[HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md) 



</td>
</tr>
<tr>
<td valign="top">

Body MIME type and Body Encoding editable



</td>
<td valign="top">

New



</td>
<td valign="top">

You can set Body MIME type and Body Encoding



</td>
<td valign="top">

[Mail Adapter](../Development/mail-adapter-f1145cc.md)



</td>
</tr>
<tr>
<td valign="top">

Add all message attachments



</td>
<td valign="top">

New



</td>
<td valign="top">

You can add all attachments contained in the message exchange to the e-mail



</td>
<td valign="top">

[Mail Adapter](../Development/mail-adapter-f1145cc.md) 



</td>
</tr>
<tr>
<td valign="top">

Create the JSON message without the root element tag



</td>
<td valign="top">

New



</td>
<td valign="top">

You can create the JSON message without the root element tag



</td>
<td valign="top">

[Define XML to JSON Converter](../Development/define-xml-to-json-converter-a60a282.md) 



</td>
</tr>
<tr>
<td valign="top">

Setting SOAP headers with Groovy script



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can set SOAP headers using Groovy script.



</td>
<td valign="top">

[Read and Modify SOAP Headers](../Development/read-and-modify-soap-headers-8a2827d.md) 



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

Dynamic attributes for the HTTP adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can dynamically configure the Address and Query field of the HTTP adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:96" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Body MIME type and Body Encoding editable



</td>
<td valign="top">

New



</td>
<td valign="top">

You can set Body MIME type and Body Encoding



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:97" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Add all message attachments



</td>
<td valign="top">

New



</td>
<td valign="top">

You can add all attachments contained in the message exchange to the e-mail



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:98" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Create the JSON message without the root element tag



</td>
<td valign="top">

New



</td>
<td valign="top">

You can create the JSON message without the root element tag



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a5ef737d7a7e41ba80245109ff39b917.xml" text="" desc="" xtrc="xref:99" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Setting SOAP headers with Groovy script



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can set SOAP headers using Groovy script.



</td>
<td valign="top">



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

Generic WSDL download



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For sender channels for which no WSDL has been specified, a generic WSDL file can be downloaded \(Integration Operations, Properties view, Services tab\).



</td>
<td valign="top">



</td>
</tr>
</table>



<a name="loio723dddb325064ffda6ae6bcca280845a__section_mgw_lkv_qdb"/>

## 01 August 2015

These release notes correspond to the customer shipment on **2015-08-01**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.26.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



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

Modelling PKCS\#7 Encryptor and Signer steps



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now model PKCS\#7 Encryptor and Signer steps using the Web-based Integration Designer.



</td>
<td valign="top">

[Sign the Message Content with PKCS\#7/CMS Signer](../Development/sign-the-message-content-with-pkcs-7-cms-signer-cc09e03.md)

[Encrypt and Sign the Message Content with PKCS\#7/CMS Encryptor](../Development/encrypt-and-sign-the-message-content-with-pkcs-7-cms-encryptor-21fd211.md)



</td>
</tr>
<tr>
<td valign="top">

Configuration setting *Proxy Type* available for HTTP adapter in Web-based Integration Designer



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

SAP Cloud Connector is supported for the HTTP adapter. The corresponding setting \(*Proxy Type*\) is now also available in the Web-based Integration Designer.



</td>
<td valign="top">

[HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md) 



</td>
</tr>
<tr>
<td valign="top">

Modelling a channel with the Mail Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now model a channel with the Mail Adapter using the Web-based Integration Designer.



</td>
<td valign="top">

[Mail Adapter](../Development/mail-adapter-f1145cc.md) 



</td>
</tr>
<tr>
<td valign="top">

Dynamically configure the mail adress and the attachment names in Mail adapter on receiver side



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now dynamically configure the mail adress and the attachment names in Mail adapter on receiver side



</td>
<td valign="top">

[Mail Adapter](../Development/mail-adapter-f1145cc.md) 



</td>
</tr>
<tr>
<td valign="top">

Updating Integration Packages and their Contents



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now choose to update your integration packages and their contents with the latest changes.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Reworked Monitoring pages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The Monitoring pages \(Message Monitor and Integration Content Monitor\) have been reworked and allow the user to do the following customize tables by adding or removing columns.

For integration flows both the display name and the technical name are shown in the filter settings and in the result tables.



</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md) 



</td>
</tr>
<tr>
<td valign="top">

XML Validator



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now validate the incoming message paylod against the configured XML schema



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="daeca02e069640d6bfcf2b27036d882a.xml" text="Validating Message Payload against XML Schema" desc="" xtrc="xref:113" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



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

Modelling a channel with the Mail Adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now model a channel with the Mail Adapter using the Web-based Integration Designer.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Dynamically configure the mail adress and the attachment names in Mail adapter on receiver side



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now dynamically configure the mail adress and the attachment names in Mail adapter on receiver side



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:115" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Product Profiles



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now consume the capabilities in product profiles at the time of designing integration flows.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

XML Validator



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now validate the incoming message paylod against the configured XML schema



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Parameterization of Timer



</td>
<td valign="top">

New



</td>
<td valign="top">

You can externalize the timer parameters. Refer to documentation for handling older integration flows with timer.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="27f4f030b2cc432f93869f9692f5f5c2.xml" text="" desc="" xtrc="xref:116" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



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

Integration flow display names



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The integration flow display name is now showed in the Operations UI, for example, in the Message Monotoring editor, the Deployed Artifacts editor, and the Conponent Status view.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Integration flow version



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The integration flow version is now displayed in the Message Monitoring editor.



</td>
<td valign="top">



</td>
</tr>
</table>

**Adapter Developer Kit**


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

Developing Adpaters



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now develop new SAP Cloud Integration adapter types on eclipse platform to extend the connectivity of SAP Cloud Integration with remote systems.



</td>
<td valign="top">

[Developing Adapters](../Development/adapter-development-process-e600fd7.md)



</td>
</tr>
</table>



<a name="loio723dddb325064ffda6ae6bcca280845a__section_g24_mkv_qdb"/>

## 04 July 2015

These release notes correspond to the customer shipment on **2015-07-04**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.25.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



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

Modeling data store operations



</td>
<td valign="top">

New



</td>
<td valign="top">

The Web-Based Designer allows you to model and specify data store operations \(for the transient data store\).



</td>
<td valign="top">

[Define Data Store Operations](../Development/define-data-store-operations-79f63a4.md) 



</td>
</tr>
<tr>
<td valign="top">

Escalation event



</td>
<td valign="top">

New



</td>
<td valign="top">

The Web-Based Designer allows you to model and specify an escalation event.



</td>
<td valign="top">

[Define an Escalation Event](../Development/define-an-escalation-event-f5b3ac8.md) 



</td>
</tr>
<tr>
<td valign="top">

PKCS\#7 Encryptor and PKCS\#7 Signer



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The Web-Based Designer allows you display PKCS\#7 Signer and Encryptor steps for imported integration flows. You cannot yet create new steps of that type.



</td>
<td valign="top">

[Sign the Message Content with PKCS\#7/CMS Signer](../Development/sign-the-message-content-with-pkcs-7-cms-signer-cc09e03.md)

[Encrypt and Sign the Message Content with PKCS\#7/CMS Encryptor](../Development/encrypt-and-sign-the-message-content-with-pkcs-7-cms-encryptor-21fd211.md)



</td>
</tr>
<tr>
<td valign="top">

Ariba Adapter for Sender and Receiver Channels



</td>
<td valign="top">

New



</td>
<td valign="top">

You configure sender and receiver channels of an integration flow with the Ariba adapter. These channels enable the SAP and Non-SAP cloud applications to send and receive business specific documents in cXML format to and from Ariba network. Examples for business documents are purchase order, invoice, etc.



</td>
<td valign="top">

[Ariba Adapter](../Development/ariba-adapter-98da76c.md) 



</td>
</tr>
<tr>
<td valign="top">

Define Script



</td>
<td valign="top">

New



</td>
<td valign="top">

You use this task to execute custom java script or groovy script for message processing



</td>
<td valign="top">

[Define a Local Script Step](../Development/define-a-local-script-step-03b32eb.md) 



</td>
</tr>
<tr>
<td valign="top">

Define the XML-to-JSON Converter



</td>
<td valign="top">

New



</td>
<td valign="top">

The XML-to-JSON converter enables you to transform messages in XML format to JSON format



</td>
<td valign="top">

[Define XML to JSON Converter](../Development/define-xml-to-json-converter-a60a282.md) 



</td>
</tr>
<tr>
<td valign="top">

Custom Functions in Message Mapping



</td>
<td valign="top">

New



</td>
<td valign="top">

You can define or modify a mapping expression by using the associated Custom Functions of a message mapping



</td>
<td valign="top">



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

Accessing MPL in the script step



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

There are the following additional Java interfaces for the message processing log \(MPL\) which you can address with the script step \(either in Groovy Script or JavaScript\): MessageLogFactory, MessageLog.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="905b24171cc746ef9069939ff3b536db.xml" text="" desc="" xtrc="xref:132" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Ariba Adapter for Sender and Receiver Channels



</td>
<td valign="top">

New



</td>
<td valign="top">

You configure sender and receiver channels of an integration flow with the Ariba adapter. These channels enable the SAP and Non-SAP cloud applications to send and receive business specific documents in cXML format to and from Ariba network. Examples for business documents are purchase order, invoice, etc.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="4c56e943ad2f4228aac5da7e62868fc9.xml" text="" desc="" xtrc="xref:133" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Connector support for IDoc adapter \(receiver channel\)



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the IDoc adapter to connect to on-premise systems via SAP Cloud Connector.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="16b2960160204db8a9c6098634593f72.xml" text="" desc="" xtrc="xref:134" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Namespace support for Xpath in *Gather* step



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can specify the namespace in Xpath if the incoming XML contains namespace.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="e7540fa25e884337891d628b7c38e6eb.xml" text="" desc="" xtrc="xref:135" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Header and property variables support for SuccessFactors SOAP adapter parameters



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can specify the key and value using header or property variables in the parameters during channel configuration



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9ffdd15d82c2479eba9f92843c97b127.xml" text="" desc="" xtrc="xref:136" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Character encoding for request payload in OData adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You have the option of specifying *UTF-8* as the character encoding format for encoding the request payload while configuring the OData adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3b52ea0b3973478094931f399f6c5696.xml" text="" desc="" xtrc="xref:137" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

Using Custom Functions in Message Mapping



</td>
<td valign="top">

New



</td>
<td valign="top">

You can create your own custom functions by using groovy scripts and use them as required.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="47729bcdec484033a044cb75303e45d9.xml" text="" desc="" xtrc="xref:138" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Connector supported for HTTP adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use the SAP Cloud Connector with HTTP adapter receiver channels to connect to on-premise systems.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="5e77b59f09e04088b0a01abb1fe4d191.xml" text="" desc="" xtrc="xref:139" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
</table>

**Additional Functions**


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

User management functions enabled for customers



</td>
<td valign="top">

New



</td>
<td valign="top">

Customers can now specify the members of their account and define their permissions.



</td>
<td valign="top">

[Adding Members to an Account](../Operations/adding-members-to-an-account-eb6d612.md) 



</td>
</tr>
</table>



<a name="loio723dddb325064ffda6ae6bcca280845a__section_hdy_mkv_qdb"/>

## 18 June 2015

These release notes correspond to the customer shipment on **2015-06-18**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.24.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/luna/](https://tools.hana.ondemand.com/luna/)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Eclipse Luna for SAP Cloud Integration

You have to use the Eclipse Luna release when you like to install the Integration Designer and the Integration Operations user interface.

There is **no support for Eclipse Kepler any more**.

An own BPMN editor comes with Eclipse Luna which provides features like the following ones:

-   Automatic connecting of shapes for sequence flows

-   Automatic adjustments of bending points of connections

-   Resizing shapes




### Features

**SAP Cloud Integration Web Application**


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

Display names for integration flows



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For integration flows display names \(instead of technical names\) are now shown in the message monitor.

In earlier versions of the software, for integration flows only a technical name \(without any spaces\) could be specified. As of this version, you have the option to specify an additional display name for integration flows in the Web-based Integration Designer. This display name can be a *human readable* name with multiple words separated by spaces. In particular, when importing an integration flow into the Web-based Integration Designer, you **have to** specify the display name mandatory.

Note the following implication when you have edited an integration flow in the Web-based Integration Designer and after that you like to import this integration flow into the Eclipse-based Integration Designer. In that case, the display name of the integration flow is shown, which might lead to confusion \(as the integration flow name in Eclipse-based Integration Designer might have *changed* that way\).



</td>
<td valign="top">

 



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

Error handling strategy for SOAP messages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

When defining the error handling strategy for SOAP messages, you can now define if in case of an exception the SOAP fault exception is to be returned to the sender system. If you don’t select this option, an error template containing the MPL ID is sent to the sender system instead.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="fb5549fb3abf4edf88606e20a73237e7.xml" text="" desc="" xtrc="xref:147" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Custom query options for OData adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can define custom query options other than the options available as a part of operations modeler when you configure the OData adapter receiver channel.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3b52ea0b3973478094931f399f6c5696.xml" text="" desc="" xtrc="xref:148" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud connector support for SOAP and OData adapter in receiver channel



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the SAP Cloud Connector with SOAP and OData adapter receiver channels to connect to on-premise systems.



</td>
<td valign="top">

-    <?sap-ot O2O class="- topic/xref " href="3b52ea0b3973478094931f399f6c5696.xml" text="" desc="" xtrc="xref:149" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 

-    <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:150" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 

-    <?sap-ot O2O class="- topic/xref " href="411ef9c366754e14bb790c6a663827ec.xml" text="" desc="" xtrc="xref:151" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 

-   [SAP Cloud Connector](https://help.hana.ondemand.com/help/e6c7616abb5710148cfcf3e75d96d596.html)




</td>
</tr>
<tr>
<td valign="top">

OData support for content enricher



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use the OData adapter and SuccessFactors OData adapter with content enricher.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="3b0c2c392f3c463aabd43f73d05b32e4.xml" text="" desc="" xtrc="xref:153" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



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

Outbound connection test for SMTP connections



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can now test an outbound connection \(for a sender mail adapter\).



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Monitoring shows now display names for integration flows.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

Instead of technical integration flow names, display names are now shown in the message monitor.



</td>
<td valign="top">



</td>
</tr>
</table>



<a name="loio723dddb325064ffda6ae6bcca280845a__section_smd_nkv_qdb"/>

## 07 May 2015

These release notes correspond to the customer shipment on **2015-05-07**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.23.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Features

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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Web-based monitoring enhancements of user interface



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

In the Message Monitor you can now open a configuration dialog for the externalized parameters of the integration flow. When you click on the status, you open the details \(message processing log\). When you click on an integration flow name, the graphical representation of the integration flow is shown \(read-only\).

In the Integration Content Monitor you can now undeploy and configure artifacts. - Specifying SAP\_sender and SAP\_Receiver With the Content Modifier you can specify additional header fields that can be used for end-to-end tracing. You can specify now the following additional fields: SAP\_Sender and SAP\_Receiver.



</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md)



</td>
</tr>
<tr>
<td valign="top">

Edit support for local integration process and sequential multicast elements



</td>
<td valign="top">

New



</td>
<td valign="top">

You can edit the properties of local integration process and sequential multicast elements in the integration flow editor.



</td>
<td valign="top">

-   [Define Local Integration Process](../Development/define-local-integration-process-520341a.md)

-   [Define Multicast](../Development/define-multicast-17de3ea.md)




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

New standard can be used to send out encrypted mails/attachments



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can configure the mail adapter on the receiver to send encrypted e-mails/attachments using S/MIME standard.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:165" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

New scheduler tab for SFTP sender adapter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can find the polling parameters under the new Scheduler tab



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="fa09f67462cd489bb6b88cf0a4dc610a.xml" text="" desc="" xtrc="xref:166" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Specifying SAP\_sender and SAP\_receiver as header elements



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

the Content Modifyer allows you to specify SAP\_sender and SAP\_receiver as header element \(that can be used for end-to-end tracing\).



</td>
<td valign="top">

 



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



<a name="loio723dddb325064ffda6ae6bcca280845a__section_vxf_nkv_qdb"/>

## 09 April 2015

These release notes correspond to the customer shipment on **2015-04-09**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.22.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Features

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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Redesign of the Monitoring pages



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

To improve usability for integration developers, the *Monitoring* pages of the Web-based SAP Cloud Integration application have been redesigned.

The Monitoring entry page is composed now of tiles that show the status of messages or integration content artifacts for specific filter criteria \(for example, for a specific status\). You can now personalize the Monitoring entry page by adding new tiles or changing existing ones or by re-arranging the tiles on the page.

The pages are designed that way that the full screen size of your device can be utilized.

To filter which messages or integration content artifacts are to be displayed, you can now select among all available statuses for messages and artifacts.

The URLs of the individual pages of the Web-based SAP Cloud Integration application can now be bookmarked.



</td>
<td valign="top">

[Monitor](../Operations/monitor-05446d0.md)



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

Receiver mail adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now configure a receiver mail adapter to send out messages by e-mail.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="08af047a0c0145ab8742b946cff7bcd7.xml" text="" desc="" xtrc="xref:175" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Streaming for XML-to-JSON converter



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The XML-to-JSON converter supports streaming.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="a5ef737d7a7e41ba80245109ff39b917.xml" text="" desc="" xtrc="xref:176" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Escalation event has



</td>
<td valign="top">

New



</td>
<td valign="top">

You can use this new step to specify an escalation event. An escalation event stops message processing without triggering further message processing retries. For synchronous messages, an error messages is sent to the sender.

A new message status *ESCALATED* has been introduced for the message monitoring.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="6126b01763be4f63b4cbb344f4c182be.xml" text="" desc="" xtrc="xref:177" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

SFAPI Parameters Support for SuccessFactors SOAP adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can specify additional SFAPI parameters for SuccessFactors SOAP adapter when you are configuring the adapter.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9ffdd15d82c2479eba9f92843c97b127.xml" text="" desc="" xtrc="xref:178" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?>  



</td>
</tr>
</table>

No new features or releases for **Integration Operations \(Eclipse\)**.



<a name="loio723dddb325064ffda6ae6bcca280845a__section_e24_clv_qdb"/>

## 12 March 2015

These release notes correspond to the customer shipment on **2015-03-12**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**1.21.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Features

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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Progress bar for integration flow opening



</td>
<td valign="top">

New



</td>
<td valign="top">

You can see a progress bar when you open an integration flow. You can also see relevant prompts in case of exceptions.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Testing message mapping



</td>
<td valign="top">

New



</td>
<td valign="top">

You can validate the correctness of message mapping with the given test input at design time.



</td>
<td valign="top">

[Testing Mappings](../Development/test-message-mapping-2718106.md) 



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

New configuration settings for the usage of XML Advanced Electronic Signature \(XAdES\).



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use XML Advanced Electronic Signature \(XAdES\) to sign messages. The Integration Designer now provides full support of the XAdES-BES and XAdES-EPES forms.



</td>
<td valign="top">

[Signing the Message Content with XML Advanced Electronic Signature](../Development/signing-the-message-content-with-xml-advanced-electronic-signature-874e032.md)



</td>
</tr>
<tr>
<td valign="top">

New algorithm can be used for message signing.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

For the Simple Signer, PKCS\#7/CMS Signer and PKCS\#7/CMS Signed and Enveloped Data, you can now use the following additional signature algorithm `RIPEMD256/RSA`.



</td>
<td valign="top">

[Message-Level Security](../ConnectionSetup/message-level-security-463a908.md)



</td>
</tr>
<tr>
<td valign="top">

Change in path traversal default in SFTP Receiver.



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

If the file contains any backward path traversals, this can lead to a potential risk of directory traversal. In such a case message processing is stopped with an error.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="fa09f67462cd489bb6b88cf0a4dc610a.xml" text="" desc="" xtrc="xref:188" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

New parameter of Receiver SOAP \(SOAP1.x\) Adapter



</td>
<td valign="top">

New



</td>
<td valign="top">

You can now select the required layout type. Options are *strict*or *lax*.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="9b619fe82f5e4ba5b7eafde67c1548a9.xml" text="" desc="" xtrc="xref:189" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Activating Tenant and Integration Flow Tracing



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

The documentation of this feature has been improved.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="866b6a94a074487384a21377ec9f2eb2.xml" text="" desc="" xtrc="xref:190" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



</td>
</tr>
<tr>
<td valign="top">

Usage of *Gather* after *Splitter* in integration flow modeling



</td>
<td valign="top">

Enhanced



</td>
<td valign="top">

You can use *Gather* after *Splitter* while modeling an integration flow.



</td>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="83e2022f9c014bebab63cb933e625610.xml" text="Defining Splitter" desc="" xtrc="xref:191" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/723dddb325064ffda6ae6bcca280845a.xml" ?> 



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



<a name="loio723dddb325064ffda6ae6bcca280845a__section_sgp_2lv_qdb"/>

## 12 February 2015

These release notes correspond to the customer shipment on **2015-02-12**.

> ### Note:  
> Note that these dates refer to planning and can be changed without further notice.

These release notes correspond to the following released software versions:

**Software Version \(Runtime\)**

**2.0.\***

\(is provided by SAP\)

> ### Note:  
> You can check whether you have this software version as follows: Open the Integration Operations perspective in Eclipse, and in the Node Explorer position the cursor on the tenant name. The software version is then displayed in a tooltip.

**Link to Eclipse Update Site**

[https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)

More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)

> ### Note:  
> Make sure that for the Integration Designer and Integration Operations tools \(to be locally installed on your client\) you use the same version as for the released SAP Cloud Integration software \(runtime components\).
> 
> You will get the actual Eclipse tool version \(according to the actually released SAP Cloud Integration software\) through this Eclipse update site:
> 
> [https://tools.hana.ondemand.com/kepler](https://tools.hana.ondemand.com/kepler)
> 
> More information: [https://tools.hana.ondemand.com/\#hci](https://tools.hana.ondemand.com/#hci)



### Features

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
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Editing an Integration Package



</td>
<td valign="top">

Enhancement



</td>
<td valign="top">

You can now save versions of artifacts irrespective of their editing status.



</td>
<td valign="top">

[Editing an Integration Package](../Development/editing-an-integration-package-155164d.md)



</td>
</tr>
</table>

No new features or releases for **Integration Designer \(Eclipse\)**.

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

Outbound connection test tool



</td>
<td valign="top">

New



</td>
<td valign="top">

You can test an outbound connection for a tenant \(calling a receiver system\). Both protocols SSL and SSH are supported.



</td>
<td valign="top">

 



</td>
</tr>
</table>

