<!-- loiob9c517ec26f74b15806526b0166c233a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Copy an MCP Server

Create a copy of an existing MCP server with all its configurations and policies intact. This can be useful when you want to create a similar artifact but with some modifications or variations.



<a name="loiob9c517ec26f74b15806526b0166c233a__prereq_rnp_v53_b2b"/>

## Prerequisites

You are assigned the *PI\_Integration\_Developer* role.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loiob9c517ec26f74b15806526b0166c233a__context_snp_v53_b2b"/>

## Context

The copy feature allows you to quickly duplicate an MCP server and make the necessary changes without starting from scratch. You can create a duplicate of an MCP server by copying it within the same package or to a different integration package. Please ensure that you explicitly update the base path of the copied artifact; otherwise, the deployment will fail.

Artifacts often have multiple policies, such as authentication, rate limiting, caching, and transformation policies. When you copy an artifact, all the policies are copied, allowing you to maintain consistency across multiple artifacts. This saves time and effort in configuring policies for each MCP server individually.

To copy an MCP server, proceed as follows:



<a name="loiob9c517ec26f74b15806526b0166c233a__steps_tnp_v53_b2b"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* from where you want to copy the MCP server.

4.  On the *<integration package\>* details page, choose *Artifacts*.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon against the required artifact and then select the *Copy* option.

6.  In the *Copy <Artifact\>* dialog box, the details for each attribute is pre-filled.

    By default, "\_copy" will get appended to the *Name*. However, you have the option to change the *Name* and provide a unique name for the MCP server you are copying. When you change the *Name*, the *ID* will be automatically generated.

    > ### Note:  
    > If you try to copy the artifact with the same name, the copy action will fail and display the following error: "The <artifact\> could not be copied because an artifact with the same ID already exists. Please edit the name to modify the ID and try again.".
    > 
    > Whether you're copying an artifact within the same integration package or a different package, you must provide a unique name for the copied artifact.

    ![](images/Copy_API_Artifact_c29a3b1.png)

    > ### Note:  
    > The name should start with an alphabet or an underscore \(\_\). It can also include numbers, spaces, periods, or hyphens \(-\), but it must not end with a period \(.\)

7.  To copy an MCP server to an Integration package of your choice, choose *Select*.

    In the *Package Selection* dialog, search for and select the desired package.

8.  Choose *Copy* to initiate the copying process.




<a name="loiob9c517ec26f74b15806526b0166c233a__result_av2_h23_31c"/>

## Results

After the copying process is finished, you will receive a success message instructing you to go to the package where the copied MCP server has been added.

You can access the MCP server in view mode, allowing you to download, deploy, and copy the artifact. If you want to delete the artifact, simply switch to edit mode by selecting the *Edit* option.

