<!-- loio1d52a7ba8c71438d90f3ea0d8e13a052 -->

# Creating Message Mapping as an Artifact

Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.

> ### Note:  
> There's the following limitation when you've chosen a runtime profile for SAP Process Orchestration \(any support package\) and you intend to use an integration flow on an SAP Process Orchestration runtime: Don't use message mapping artifacts. Instead, define the message mapping as a flow step in the integration flow.

Message mapping as an artifact consists of a mapping definition \(\*.mmap\) file that is created or imported by a user. When you build your integration scenario, you can refer these artifacts from a message mapping step in the integration flow.



<a name="loio1d52a7ba8c71438d90f3ea0d8e13a052__section_izl_glr_4pb"/>

## Benefits of Using Message Mapping Artifacts

-   **Reusability** – Refer the mapping artifacts in multiple integration scenarios instead of manually uploading them every time and avoid duplicates.

-   **Reduce Maintenance Efforts** – By referring the artifact from a single place, you only have to edit the artifact once if there are changes needed.

-   **Reduce File Size and Memory Usage** – By avoiding multiple upload instances you can get extra storage space.


<a name="task_nn4_rhj_syb"/>

<!-- task\_nn4\_rhj\_syb -->

## Create a Message Mapping Artifact



<a name="task_nn4_rhj_syb__prereq_fwz_thj_syb"/>

## Prerequisites

You've created an integration package and opened it in edit mode.



<a name="task_nn4_rhj_syb__context_cnt_xhj_syb"/>

## Context

Create a new message mapping artifact that consists of source and target schema files. With the help of the mapping editor you can add schema files, define mapping between source and target messages, and create a groovy script to consume user-defined Functions \(UDFs\).



<a name="task_nn4_rhj_syb__steps_frk_thj_syb"/>

## Procedure

1.  In the *Artifacts* tab of the integration package, choose *Add* \> *Message Mapping*.

2.  In the dialog box that comes up, choose *Create*.

3.  Provide a name, ID, and an optional description for the message mapping.

4.  Choose *Add*.

    A message mapping artifact is created.

5.  Open the message mapping artifact and choose *Edit* to add source and target messages, create mappings, and perform operations. Choose *Save*.

6.  Choose *Deploy*.

    Before consuming a message mapping artifact, you must first deploy it.


<a name="task_lt2_zhj_syb"/>

<!-- task\_lt2\_zhj\_syb -->

## Upload a Message Mapping Artifact



<a name="task_lt2_zhj_syb__prereq_xcv_13j_syb"/>

## Prerequisites

-   You've created an integration package and opened it in edit mode.

-   You've a message mapping artifact downloaded in your file system. The downloaded artifact can be from the same tenant or a different one.




<a name="task_lt2_zhj_syb__context_vhd_b3j_syb"/>

## Context

Use this option to upload a message mapping artifact stored on your computer. Once selected, you can upload a message mapping definition as a zip file from your file system.

> ### Note:  
> While uploading a message mapping artifact, make sure that the file is compatible with the service plan of your tenant. If your tenant doesn't support function libraries or message type artifacts and you attempt to upload a message mapping artifact that contains them, you must rework on your mapping that isn't a good experience. See SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).
> 
> If the function libraries or message type artifacts are consumed in the mapping, you face an error stating that you can't consume the mapping. If the function libraries or message type artifacts are referred \(not consumed\) in the mapping, you don't see the references at all in the mapping.



<a name="task_lt2_zhj_syb__steps_nrf_pzj_syb"/>

## Procedure

1.  In the *Artifacts* tab of the integration package, choose *Add* \> *Message Mapping*.

2.  In the dialog box that comes up, choose *Upload*.

3.  Choose *Browse* to upload a .zip file that contains the message mapping content.

4.  Provide a name, ID, and an optional description for the message mapping.

5.  Choose *Add*.

    A message mapping artifact is created.

6.  Open the message mapping artifact and choose *Edit* to change the source and target messages, create mappings, and perform operations. Choose *Save*.

7.  Choose *Deploy*.

    Before consuming a message mapping artifact, you must first deploy it.


<a name="task_hcc_c3j_syb"/>

<!-- task\_hcc\_c3j\_syb -->

## Import a Message Mapping from ES Repository



<a name="task_hcc_c3j_syb__prereq_xty_d3j_syb"/>

## Prerequisites

-   You've created an integration package and opened it in edit mode.

-   You've established connection to your SAP Process Orchestration system. See: [Configuring Connectivity to an SAP Process Orchestration System](../IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).




<a name="task_hcc_c3j_syb__context_yty_d3j_syb"/>

## Context

Use this option to import a message mapping object from the Enterprise Services Repository \(ES Repository\).



<a name="task_hcc_c3j_syb__steps_czl_jbk_syb"/>

## Procedure

1.  In the *Artifacts* tab of the integration package, choose *Add* \> *Message Mapping*.

2.  In the dialog box that comes up, choose *ES Repository*.

3.  In the *Name* list, select an ES Repository from the list of connected systems.

    The *Address* and *Location ID* of the selected ES Repository comes up.

4.  Choose *Connect*.

    A list of message mapping objects from the ES Repository comes up.

5.  Select a message mapping object that you want to import. Choose *Next*.

6.  In the *Dependent Resources* tab, provide a name, ID, and an optional description for the message mapping artifact. You also see a list of dependent files of the message mapping object like function library objects and WSDL files that are to be imported too. Choose *Next*.

7.  Optional, only if the source message mapping object has function library objects: Select one or more Function Libraries artifacts to contain all dependent function library objects of the source mapping object.

    In , a function library object from ES Repository must be imported to a Function Libraries artifact. You can't add a function library object directly to a message mapping or an integration package. See:  <?sap-ot O2O class="- topic/xref " href="dd8c30d1c103437298f173fa5d06e96c.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/1d52a7ba8c71438d90f3ea0d8e13a052.xml" ?> .

8.  Choose *Add*.

    A message mapping artifact is created.

    If there are dependent function library objects, they are imported to the selected Function Libraries artifact. References to the dependent function library objects are also created.

9.  Open the message mapping artifact and choose *Edit* to change the source and target messages, create mappings, and perform operations. Choose *Save*.

10. Choose *Deploy*.

    Before consuming a message mapping artifact, you must first deploy it.


