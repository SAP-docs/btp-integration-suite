<!-- loio09400a29943b44ab88764295d7cbb2c9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import and Export Agreements

Import and export Agreements.

There could be scenarios where you need to export or import the trading partner agreements from one tenant to another tenant. The *Cross Actions* tab in the application helps you to achieve this seamlessly. Using this tab, you can export and import agreements in bulk along with their MIG and MAG references in `.zip` format. To do so, follow the procedure below.

1.  Login to your application ad navigate to *Design* \> *B2B Scenarios*.

2.  Navigate to the *Cross Actions* tab and choose *Export and Import*.
3.  In the resulting dialog box, choose either of the following based on your requirement:
    1.  *Export Agreement*: If you want export agreements from this tenant to another tenant.

    2.  *Import Agreement*: If you want to import agreements into this tenant.




<a name="loio09400a29943b44ab88764295d7cbb2c9__section_i4v_wdw_pxb"/>

## Export Agreements

If you chose *Export Agreement*,

1.  Enter a meaningful name in the *Action Name* field.

2.  Enter a *Description*. This is optional.
3.  Choose *Create*.
4.  In the *1. Select Agreements* step, select an agreement name from the drop-down list of the *Agreement Name* field and choose *Go*. You can also select multiple agreement names using the drop-down option.
5.  You can refine the search using the following options:

    -   *Trading Partner*: Select a trading partner from the drop-down list.

    -   *Activation Status*: You can select agreements that are in *Draft* state or *Active* state.
    -   *Created By*: Enter the email address of the user who created the agreements.
    -   *Last Modified Date*: Choose the last modified date of the agreement.

    > ### Note:  
    > The maximum number of agreements allowed per import is 300.
    > 
    > You can only choose agreements with complete configuration. Agreements with incomplete configuration will cause the export to fail.

6.  The agreements list based on your search is displayed below the fields. Select the agreements from the list that you wish to export and choose *Next*.
7.  In the next step *2. Configure Export options*, set the export options for the following:

    -   *Identifiers*: Choose
        -   *Export All* if you want to export all the identifiers

        -   *Export Placeholders for Type System* if you want to export placeholders for Identifier IDs based on the type system. On selecting this option the drop-down box near it gets enabled.

            Use the drop-down list to select the Type System. For the identifiers in the selected Type System, their *Identifier ID* will be skipped and other properties such as, ID, Alias, Scheme Name and Agency will be exported. For other Type Systems, all properties of the Identifiers will be exported.


    -   *System Communications Channels*: Choose
        -   *Export Placeholder* to only export the Name, Alias, Description, Direction and Adpater Type.
        -   *Export All* to export the complete adapter configuration.

        -   *Skip* to export only the Alias information.

    -   *Parameters*: Choose
        -   *Export All* to export all configuration parameters.

        -   *Skip* to skip the export of all parameters.

    -   *Security*: Choose
        -   *Export All* to export all security configurations except the certificate aliases.

        -   *Skip* to skip the export of all security information.


    Choose *Next* after maintaining the field values.

8.  The next step allows you to review your choices and the agreement list. Choose *Finish* to execute the export.
9.  Under the *Action Logs* table, you can see the progress of your export. Choose and open your action log to view the export in detail.
10. The <span class="SAP-icons-V5"></span> icon next to your action log contains the following options :
    -   *Edit*: This option allows you to edit the *Name* and *Description* of the action.

    -   *Resubmit*: This option will create a new task with the same set of selections.
    -   *Delete*: This option deletes the entire action.

11. Choose *Download* to download the exported artifacts in a `.zip` format.



<a name="loio09400a29943b44ab88764295d7cbb2c9__section_srq_hhw_pxb"/>

## Import Agreement

If you chose *Import Agreement*,

1.  Enter a meaningful name in the *Action Name* field.

2.  Enter a *Description*. This is optional.
3.  Choose *Create*.
4.  In the resulting dialog box, choose *Browse* for the field *File to import* to browse and upload a `.zip` file.

    > ### Note:  
    > The maximum number of agreements allowed per import is 300.

5.  Under the *Configure Import Options*, maintain the following fields:
    -   *Single Identifiers*: Choose

        -   *Create Only* if you want to create the identifiers in the system.

        -   *Create or Overwrite* if you want to import the values or, overwrite them in the system if the alias matches. To know more about aliases, see [Understanding the Basic Concepts](../understanding-the-basic-concepts-74c068d.md).
        -   *Skip* if you want to skip the import of the identifiers.

    -   Similary, set the values for the field *Identifier Groups*.
    -   For the field *Identifiers in Groups*, select:
        -   *Import Empty Groups*: If you want to import just the identifier groups without the identifiers within them, choose this option.

        -   *Import Identifiers in Groups \(exclude conflicting Identifiers\)*: If you want to import the groups and the identifers within them, choose this option. This will however exclude the identifiers than conflict with identifiers already existing in the system.
        -   *Import Identifiers in Groups \(include conflicting Identifiers\)*: If you want to import the groups and the identifiers within them, including even the ones that conflict with the identifiers existing already in the system, choose this option.

    -   Set the values for the field *System Communication Channels* similar to the identifiers field.
    -   For the fields *Parameters*, *Activity Paramaters* and *Security*, choose:
        -   *Create or Overwrite* if you want to import the values or, overwrite them in the system if the alias matches. To know more about aliases, see [Understanding the Basic Concepts](../understanding-the-basic-concepts-74c068d.md).
        -   *Skip* if you want to skip the import of the identifiers.

    -   For the fields *MIG References* and *MAG References*, choose:

        -   *Import* if you want to import all MIG/MAG references. This will work only if the exact version of the referenced MIG/MAG exists in the importing system. If not, the import will throw an error.

        -   *Update to the latest version* when there is a higher version of the MIG/MAG in the importing system and you want to update your MIG/MAG references to that version. However, if there is no corresponding MIG/MAG available in the system, an error will be thrown.
        -   *Skip* to skip importing MIG/MAG references of your agreements.

        To know how to export and import MIGs/MAGs seperately, see [Import and Export](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/import-and-export?version=Cloud).


6.  After setting all the relevant fields, choose *Import*.
7.  Under the *Action Logs* table, you can see the progress of your import. The status shows *Completed* once the progress is finished. Choose and open your action log to view the import in detail.

