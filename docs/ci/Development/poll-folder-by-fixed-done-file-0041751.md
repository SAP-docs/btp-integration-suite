<!-- loio0041751c99dc45269597d0d1ef1e2182 -->

# Poll Folder by Fixed Done File

Learn how to poll a complete folder with all the files of the path triggered by a fixed done file.

This section shows you how to configure the SFTP Sender Adapter.

For more information about the SFTP adapter, see [SFTP Adapter](sftp-adapter-e3dce88.md).



<a name="loio0041751c99dc45269597d0d1ef1e2182__section_pgd_w51_srb"/>

## Implementation

To showcase how to poll a folder triggered by a done file, use a simple scenario. The example integration flow **File Transfer – Poll Folder by Fixed Done File** is designed the following way:

![](images/2112_File-Transfer_Poll-Folder-by-Fixed-Done_File_1_integration-flow_26b37bf.jpg)

In the *Source* tab of the SFTP sender adapter, enter the *Directory*, *Address* of the SFTP server \(`host:port`\), *Proxy Type* \(On-Premise/Internet\), *Location ID* \(if On-Premise\) and *Credential Name* to access the SFTP server. Those parameters are externalized so that you can use your own SFTP server. See [Configure Externalized Parameters of an Integration Flow](configure-externalized-parameters-of-an-integration-flow-462a478.md).

The *File Name* remains empty so that all files in the path are read.

![](images/2112_File-Transfer_Poll-Folder-by-Fixed-Done_File_2_source-tab_aaf9fd4.jpg)

In the *Processing tab*, select the *Done File Expected* as *Read Lock Strategy*. This way no file is read until the done file entered in next field is available in the same directory of the SFTP server.

In the *Done File Name*, enter the name of the done file. It is also externalized. This way, the files of the folder will be read simultaneously when the specific file is in the folder. Each file will create a new instance of the integration flow.

Once one of the files has been successfully processed, the done file is deleted from the SFTP server. If one of the other files generates an error in the integration flow, this file remains in the SFTP server but will not be processed again, as the done file is already deleted. If you like to get the file processed, you have to put a done file into the folder again.

> ### Note:  
> The SFTP sender adapter does not check if the done file has a newer timestamp than the files to be read.

![](images/2112_File-Transfer_Poll-Folder-by-Fixed-Done_File_3_processing-tab_7ec381d.jpg)

Once the scenario is executed, it creates a new entry in the Data Store *FileTransfer- pollFolderByFixedDoneFile* with the content of the file read.

