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
> While uploading a message mapping artifact, make sure that the file is compatible with the service plan of your Integration Suite tenant. If your tenant doesn't support function libraries or message type artifacts and you attempt to upload a message mapping artifact that contains them, you must rework on your mapping that isn't a good experience. See SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).
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

## Import a Message Mapping from Enterprise Services Repository \(ESR\)



<a name="task_hcc_c3j_syb__prereq_xty_d3j_syb"/>

## Prerequisites

-   You've established connection to your SAP Process Orchestration system. See: [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   You've created an integration package and opened it in edit mode.




<a name="task_hcc_c3j_syb__steps_czl_jbk_syb"/>

## Procedure

1.  In the *Artifacts* tab of the integration package, choose *Add* \> *Message Mapping*.

2.  In the dialog box that comes up, choose *ES Repository*.

3.  In the *Name* list, select an ES Repository from the list of connected systems.

    The *Address* and *Location ID* of the selected ES Repository comes up.

4.  Choose *Connect*.

    A list of message mapping objects from the ES Repository comes up.

5.  Select a message mapping object that you want to import. Choose *Next*.

6.  In the *Dependent Resources* tab, provide a name, ID, and an optional description for the message mapping artifact. You also see a list of dependent objects like function library, message type, archives, andWSDL files that are to be imported too. Choose *Next*.

    1.  Optional: If there are dependent message type objects, choose *Import Message Types as WDSLs* to convert the message type objects as WSDL files during the import.

        > ### Note:  
        > Until the May 2024 release of SAP Integration Suite, message types were automatically converted as WSDL files. The checkbox helps you maintain backward compatibility and avoid any regressions.

        > ### Remember:  
        > It is possible for multiple dependent Message Type objects to have the same name but different namespaces. When you import such message type objects as WSDL files, only one WSDL file gets uploaded as the uniqueness is dependent on the filename. Make sure that you keep the same name only for one WSDL file in the ES Repository and rename the other files. This makes sure that individual WSDL files are created in SAP Integration Suite for each Message Type. If you don't do this, the nodes where the WSDL files are used become empty and eventually the message mapping artifact goes into an erroneous state.


7.  Optional, only if the source message mapping object has dependent function library objects or imported archives objects: In the *Import Function Libraries* tab or *Imported Archives* tab, select one or more function libraries or imported archives artifacts, respectively, to contain all dependent objects of the source mapping object.

    In SAP Integration Suite, a function library or imported archives object from the ES Repository must be imported to a function libraries artifact or an imported archives artifact, respectively. You can't add a function library or imported archives object directly to a message mapping or an integration package. See: [Working with Function Libraries](working-with-function-libraries-dd8c30d.md) and [Working with Imported Archives](working-with-imported-archives-e00e81d.md).

    > ### Remember:  
    > The dependent archive objects of the function library object are not imported. You must manually import the archive object and refer the same in the Function Libraries artifact. For more information, see: [Consuming Imported Archives](consuming-imported-archives-e7562a7.md).

8.  Optional, only if the source message mapping object has dependent message type objects: In the *Import Message Types* tab, see a list of message type objects and understand their metadata. Choose *Next*.

    1.  Choose *Include Dependent Data Types* if you would like to import the associated data type objects as well.


9.  Optional, only if the source message mapping object has dependent message type objects: In the *Import DT Dependencies* tab, see the import status of the message type and data type objects. Choose *Next*.

10. Choose *Submit*.

    A message mapping artifact is created.

    If there are dependent objects, they are imported appropriately. References to the dependent objects are also created.

    Cloud Integration supports the import of PI/PO message mapping objects with simple type parameters of the kind import. The imported parameters are used as message properties and are automatically pre-filled in the standard built-in functions wherever they are defined in the PI/PO message mapping object. For more information, see [Parameterized Mapping Programs](https://help.sap.com/docs/SAP_NETWEAVER_750/0b9668e854374d8fa3fc8ec327ff3693/4bf4190deaca4c86e10000000a42189e.html).

    > ### Note:  
    > Import type parameters are now supported and are used or rendered in the expression editor for built-in functions. Although export and adapter \(channel\) type parameters are shown, they are not used or rendered within the message mapping expression editor in Integration Suite.
    > 
    > The import functionality for message mapping with parameters is not supported for local message mappings in integration flows.

11. Open the message mapping artifact and choose *Edit* to change the source and target messages, create mappings, and perform operations. Choose *Save*.

12. Choose *Deploy*.

    Before consuming a message mapping artifact, you must first deploy it.


