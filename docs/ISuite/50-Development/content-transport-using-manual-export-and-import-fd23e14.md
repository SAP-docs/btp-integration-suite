<!-- loiofd23e1479cce4cac8fce64d605420e15 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Content Transport using Manual Export and Import



<a name="loiofd23e1479cce4cac8fce64d605420e15__prereq_mrc_c3j_z1b"/>

## Prerequisites

You have logged in to SAP Cloud Integration on source and target tenants. Access the :pencil2:\(*Design*\) tab \(workspace\).



## Context

One of the options to transport content from one tenant to another is to use the *Export* and *Import* options for your integration package. The application imports the integration package to your local file system in the form of a *.zip* file. You can import the same file in the target tenant using the *Import* option.



## Procedure

1.  Select the integration package that you want to export.

2.  Choose *Export*.

    A *.zip* file is downloaded to the default browser download location on your local file system.

3.  Log in to the SAP Cloud Integration web application to which you want to import the content. Choose :pencil2:.

4.  Choose *Import*.

    A new window opens in your file system explorer, allowing you to access your local file system.

5.  Navigate to the folder path where the *.zip* file was downloaded in step 3.

6.  Select the file and choose *Open*.

    You see a prompt indicating the successful import of the *.zip* file. You can see the imported integration package in the *Design* tab of your target tenant.


