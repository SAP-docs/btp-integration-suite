<!-- loio2e3cf3b4b8e7458195c0f03fe400e050 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Various Types of Body Files in the Simulation

Use simulation input to upload the payload content. You can simulate Zip and Tar splitters, which require an incoming payload in Zip and Tar format.



## Context

You can experience the following behaviour while providing input payload.

-   Upload the trace message content in zip comprising of file types such as `*.header`, `*.properties`, and `*.body`.

-   Any modification in the contents of the `*.body` file that has readable contents, for example, xml, json, text, etc., invalidates the file and simulate the modified content.
-   If you would like to reset the modified content of the file, you can perform using *Reset* option, that brings back the file you uploaded.
-   You can upload any other body input files such as `*.tar`, `*.txt`, `*.xlsx`, `*.pdf`, etc., via *Upload from File System*.



## Procedure

Here's how you can add simulation input while you’re working with integration flow simulation.

1.  Identify a subset of an integration flow that you would like to simulate.

2.  Choose <span class="SAP-icons-V5"></span> start point of the simulation on identified connection to begin.

3.  A dialog opens to add a simulation input. Add the necessary details.

    -   You can add input that could be of *Headers* or *Properties* or *Body*.

    -   You can also upload input payload from your local file system.

4.  To add *Header*, choose *Add* button and enter the *Name* and *Value*.

5.  To add *Properties*, choose *Add* button and enter the *Name* and *Value*.

6.  To upload your local file, choose *Upload from File System* that automatically fetches all the values.

7.  If you have chosen to upload the file, the file appears in the *Body* section and the content is displayed.

    > ### Note:  
    > -   A file with binary content can't be displayed in the body section. The file supports encoding in UTF8 format only.
    > 
    > -   You can modify the content by choosing *Edit* option.
    > 
    > -   If you don't want the modified content to be simulated, select *Reset* option and that brings back the uploaded file.

8.  Choose *OK*.


**Related Information**  


[Configure Simulation](configure-simulation-45a71f8.md "Use Simulation feature to test an integration flow and check the desired outcome even before the deployment.")

