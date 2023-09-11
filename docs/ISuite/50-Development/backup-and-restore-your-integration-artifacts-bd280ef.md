<!-- loiobd280efbae9e4d24ab24c62b02f16028 -->

# Backup and Restore Your Integration Artifacts



## Context

Download all the artifacts of a package in one go, using which you can create a local backup of all artifacts. Later, you can upload the downloaded resources in another package or tenant based on your requirements.



<a name="loiobd280efbae9e4d24ab24c62b02f16028__steps_ms4_mq4_ppb"/>

## Procedure

1.  Open your integration package and choose *Edit*.


Download all artifacts

2.  Choose the *Artifacts* tab.

3.  Select the checkbox besides the column header *Name* to select all the integration artifacts in the package. Alternatively, you can select only the artifacts that you would like to download.

4.  Choose *Actions* \> *Download*.

    A .zip file with filename same as the integration package's name is ready for download.

5.  Save the file to your choice of destination.

    > ### Remember:  
    > The folder structure of the mass download file is different from the structure of an individually downloaded artifact. In a mass download, the .zip file contains individual folders for each artifact. In turn, each folder contains the resources of an artifact. But, in an individual download, the downloaded .zip file directly contains the resources of the artifact.
    > 
    > This information is critical to know because when you attempt to upload the downloaded resources in another package, you can't directly upload the mass-downloaded .zip file.


To upload the downloaded artifacts in another package or tenant, continue with the below steps.

6.  Choose *Design* \> *Integrations*.

7.  Choose *Import*.

8.  Browse and select a .zip file.

    > ### Remember:  
    > Upload a .zip file that contains multiple .zip files for each artifact. Each .zip file of the artifact must contain the resources directly in it and not within a folder.


