<!-- loioc3a913ea20544d76ae4e55d3c44e0a1d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying Data Flows



## Context



## Procedure

1.  In the *Integration Package Editor*, in the *Artifacts* section, select the required data flow from the list.

2.  Choose :gear:to *Deploy*.

3.  In the *Settings* dialog box that appears, enter the following details:

    -   Data Center URI
    -   Application Name
    -   Organization Name

    Once you enter the above mentioned details, the application forms the Data Service URL.

4.  Choose *OK*.

5.  In the *LOG ON* screen that appears, enter the organization name.

6.  Choose *Log On*.

    The Data Integration application opens its *Projects* tab.

7.  In the dialog box that appears, enter the following details as required:

    -   Name
    -   Source
    -   Target

8.  Choose *OK*.

    The newly deployed data flow appears as an entry in the *Projects* tab page. If required, you can switch back to the SAP Cloud Integration Web application.

    > ### Note:  
    > To switch to SAP Cloud Integration Web Catalog view from Data Integration using the [Back Button\] in the browser, perform the required substeps:
    > 
    > -   If you use Internet Explorer, from the context menu of [Back Button\], select Cloud Integration.
    > -   If you use Google Chrome, click twice on[Back Button\].
    > -   If you use Mozilla Firefox, from the context menu of [Back Button\], select Cloud Integration .
    > 
    > If you want to switch to SAP Cloud Integration Web *Catalog* view from Data Integration using the [Forward Button\] in the browser then by default, it displays the *Projects* tab page without the Settings option. This behavior remains the same for Internet Explorer, Google Chrome, and Mozilla Firefox.
    > 
    > If you do not have authorization to access the Data Integration application then you get the following error messages:
    > 
    > -   Error message for Google Chrome and Mozilla Firefox:
    > 
    >     User is not included in the organization. Contact your security administrator for assistance.
    > 
    > -   Error message for Internet Explorer:
    > 
    >     HTTP 404: Not found error


