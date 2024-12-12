<!-- loioe7562a794581407ea209274104c283e4 -->

# Consuming Imported Archives

Understand how to consume an imported archive object in a Function Libraries artifact.



<a name="loioe7562a794581407ea209274104c283e4__prereq_i5s_mhv_fbc"/>

## Prerequisites

1.  [Reuse Imported Archives Objects from ES Repository](reuse-imported-archives-objects-from-es-repository-4196091.md)

2.  Deploy the Imported Archives artifact.




<a name="loioe7562a794581407ea209274104c283e4__context_hdr_4hk_2bc"/>

## Context

Consuming an imported archive object is a two-step process:

1.  Create an artifact-to-artifact reference – create a reference from the Function Libraries artifact to the Imported Archives artifact. You can refer to the same Imported Archives artifact from multiple Function Libraries artifacts.

2.  Use the archive in a function library object – add the archive object to one of the function library objects. You can add the same archive object to multiple function library objects.


<a name="task_jlb_j42_2bc"/>

<!-- task\_jlb\_j42\_2bc -->

## Creating a Reference With Function Libraries Artifact



<a name="task_jlb_j42_2bc__prereq_vj1_m42_2bc"/>

## Prerequisites

[Import Function Library from ES Repository](import-function-library-from-es-repository-d6e7585.md)



<a name="task_jlb_j42_2bc__steps_wj1_m42_2bc"/>

## Procedure

1.  Open the Function Libraries artifact in edit mode.

2.  In the left-side resource pane, choose the *References* tab.

3.  Choose *Add References* \> *Imported Archives*.

4.  Choose one or more integration packages.

    All Imported Archives available in the selected packages appear.

5.  Choose one or more Imported Archives artifacts based on your requirement and choose *OK*.

6.  Choose *Save* to save the Function Libraries artifact.


<a name="task_w33_x42_2bc"/>

<!-- task\_w33\_x42\_2bc -->

## Add an Imported Archive Object To The Function Library Object



<a name="task_w33_x42_2bc__steps_y33_x42_2bc"/>

## Procedure

1.  Open the Function Libraries artifact in edit mode.

2.  In the left-side resource pane, choose the *Function Libraries* tab.

3.  Choose a function library object.

    The java class opens up in the editor.

4.  In the right side editor, choose the *Archives Used* tab.

5.  Choose *Add* and select an imported archive. Choose *OK*.

6.  Change the code for loading the archive object.

    The default line of code that comes with an ESR object is as follows:

    `InputStream in = this.getClass().getClassLoader().getResourceAsStream("com/customer/appl/MyConfig.properties");`

    For the function library object to be able to rightly fetch the imported archive object in Integration Suite, change the existing code line as follows:

    `InputStream in = super.loadResourceFromArchive("ID of the Imported Archive artifact", "path of the file in archive");`.

7.  Choose *Save* to keep your changes and add archive object to the Function Libraries artifact.


