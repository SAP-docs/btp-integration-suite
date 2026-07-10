<!-- loio41960910f60148a29531229a9e952642 -->

# Reuse Imported Archives Objects from ES Repository



<a name="loio41960910f60148a29531229a9e952642__prereq_kjm_4zv_4xb"/>

## Prerequisites

-   [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md)

-   [Creating an Imported Archives Artifact](creating-an-imported-archives-artifact-e555caf.md)




<a name="loio41960910f60148a29531229a9e952642__context_fsn_mfv_fbc"/>

## Context

There are certain limitations while importing and consuming the imported archive objects:

-   You can import archive objects with XSLT mapping but you can't assign the mapping to a *XSLT Mapping* flow step.

-   You can import archive objects with Java mapping but you can't assign the mapping to an *Operation Mapping* flow step.

-   You must maintain custom java code in an imported archive for any underlying Java version changes or platform dependencies changes.




## Procedure

1.  Open the Imported Archives artifact that you created and choose *Edit*.

    The resource pane and editor comes up on the left and right sides respectively.

2.  In the resource pane, choose *Upload*.

3.  In the dialog box, choose *ES Repository* as the *Source*.

4.  Select the *Name* of the ES Repository that you want to connect with.

    You see the details populated in the *Address* and *Location ID* fields.

5.  Choose *Connect*.

    You see a list of available imported archive objects.

6.  Choose an imported archive object of your choice and choose *Select*.

    The selected imported archive object gets imported to the resource pane.

7.  Choose the imported archive object to view its content.

    The contents of the archive object appear in the editor pane. You see the name and path for all files contained in the archive object.

8.  Choose *Save*.

9.  Deploy the Imported Archives artifact.


