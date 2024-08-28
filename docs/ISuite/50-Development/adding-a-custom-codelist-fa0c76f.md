<!-- loiofa0c76f3a3834580be89674c25c5a230 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding a Custom Codelist

Create and add a codelist to the custom type system Custom Codelist.



## Context

Follow the procedure to add a codelist to a custom codelist.



## Procedure

1.  Navigate to the *Custom Type Systems* <span class="SAP-icons-V5"></span> from the left pane of your application.

2.  Choose the *Custom Codelists* and navigate to the *Codelists* tab.

3.  Choose *Add* and maintain the following parameters:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **ID**
    
    </td>
    <td valign="top">
    
    Enter an ID for the codelist
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Name**
    
    </td>
    <td valign="top">
    
    Enter a meaningful name for your codelist
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Definition**
    
    </td>
    <td valign="top">
    
    Provide a decription for the codelist. You can select the *Formatted Text* checkbox if you want the description to be formatted.
    
    </td>
    </tr>
    </table>
    
4.  Select the checkbox for *Copy code values from Codelist* if you want to copy existing code values to your custom codelist.

    1.  If selected, you have to maintain the following fields that appear:

        1.  *Type System*: Select the value help <span class="SAP-icons-V5"></span> button to select the type system. You can switch between *Standard* and *Custom* type systems in the resulting dialog and select a type system from the list.

        2.  *Codelist*: Select a codelist from the list using the drop-down <span class="SAP-icons-V5"></span> button. The drop-down list displays the codelists pertaining to the type system you selected.

        3.  *Version*: Select a codelist version from the list using the drop-down <span class="SAP-icons-V5"></span> button.


    2.  The available code values of the selected codelist gets displayed in the table below these fields. Use the checkbox to select the required code values.

    3.  You can also use the **Search** option to search for specific code values. If you want to select all the values, use the *Select All* checkbox.


5.  Choose *Create*. This will create and open the codelist.

6.  In the *Code Values* tab of the codelist, you can start adding the code values by choosing *Add an Entry*. This will add an entry in the table with no values. You can then maintain the necessary detail.

7.  The drop-down <span class="SAP-icons-V5"></span> button next to *Add an Entry* provides other means of adding codelists:

    1.  *Add from CSV file* allows you to upload code values using a csv file. Choose this option and in the resulting dialog, choose *Select* to browse and upload your csv file.

        If you do not have a csv file but need to know how to create and upload a csv file, refer the section **Creating codelists using a csv file** below.

    2.  *Add from other codelists* allows you to add code values from existing codelists in the system. Select this option and in the resulting dialog, maintain the following:

        1.  *Type System*: Select the value help <span class="SAP-icons-V5"></span> button to select the type system. You can switch between *Standard* and *Custom* type systems in the resulting dialog and select a type system from the list.

        2.  *Codelist*: Select a codelist from the list using the value help <span class="SAP-icons-V5"></span> button.

        3.  *Version*: Select a codelist version from the list using the drop-down <span class="SAP-icons-V5"></span> button.

        4.  Choose *Next*. The next step displays all the code values pertaining to the codelist you selected. All the values are selected by default.
        5.  Select the required code values from the list and choose *Add Code Values*.


8.  Choose *Save* to save your changes.

9.  Choose *Activate* to activate your codelist. Once activated, the codelist becomes read-only. You need to create a new draft version of the codelist to edit further.

10. To delete a codelist, see [Deleting a Custom Codelist](deleting-a-custom-codelist-01ad9ee.md).


<a name="task_w4b_4l5_tbc"/>

<!-- task\_w4b\_4l5\_tbc -->

## Creating codelists using a csv file

Create a codelist using a csv file.



<a name="task_w4b_4l5_tbc__steps_tdt_yl5_tbc"/>

## Procedure

1.  In the *Code Values* tab of the codelist, choose the <span class="SAP-icons-V5"></span>next to *Add an Entry* and choose *Add from CSV file* to upload a csv file.

2.  In the *Code Value Upload* dialog, choose *How to...* \> *Download the template\(\*.csv\)* option. This will download the csv file template locally with the name `CodeValueDownload.csv`

3.  Edit the downloaded template file `CodeValueDownload.csv` to enter the required values and save.

    Ensure you do not change or remove the header of the template.

4.  Once done, you can choose *Select* to upload the updated file containing code values in the *Code Value Upload* dialog.

    > ### Note:  
    > You can also download a standard codelist from a type system in `csv` format and upload it here. To do so,
    > 
    > -   Go to *Type Systems* and open the type system that you require.
    > 
    > -   Navigate to the *Codelists* tab and select a version of the codelist that you want to download.
    > -   In the *Code Values* tab, choose *Download*. This will download the standard codelist in `csv` format.

5.  If the csv file contains any code value with an escape character, on uploading the file the list of those code values are displayed. Select the rows for which you want the escape character to be removed and choose *Remove*.

6.  If you want to skip this step, choose *Skip All*.

7.  If you want to add more code values to the uploaded values, choose *Add* and enter the required fields in the new entry.

    > ### Note:  
    > You can use the upload option even if code values exist already. The code values in the file get appended to the existing list. However, if there are conflicting values between the list and the csv file, during upload the dialog box displays the list of already existing values. You can select the checkbox of those values that you wish to overwrite and choose *Overwrite*.


