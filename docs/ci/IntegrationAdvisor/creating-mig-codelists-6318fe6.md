<!-- loio6318fe606a8f44a88d6cc2255c06ee1e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating MIG Codelists

If the reusable or type-system based codelists don’t meet your requirements, you can create new message implementation guideline \(MIG\) codelists.



<a name="loio6318fe606a8f44a88d6cc2255c06ee1e__prereq_e32_pzl_fpb"/>

## Prerequisites

You’ve opened the message implementation guideline in the edit mode.

<a name="task_ahs_bcp_gpb"/>

<!-- task\_ahs\_bcp\_gpb -->

## Adding Code Values



<a name="task_ahs_bcp_gpb__steps_fxv_q2p_gpb"/>

## Procedure

1.  On the *MIG Codelists* tab, choose *Create* to create a new codelist.

2.  Specify the codelist identifier, name, and definition in the corresponding fields under *MIG Codelists*.

3.  Choose *Code Values*.

4.  On the *Code Values* tab, add new code values by choosing one of the following options:

    -   *Create*: Enter a value, name, and definition.
    -   *Create* \> *Create Empty Code Value*: Enter a name and definition. The value `(empty)` is not editable.
    -   *Upload*: Import a CSV file containing code values. See the section *Adding Code Values by Uploading a CSV File*.

5.  You can download the code values in **CSV** format using the *Download* option. The downloaded file corresponds to the CSV template used for the codelist upload. You can use it, for example, to update the downloaded CSV file and re-upload it.


<a name="task_rym_x3p_gpb"/>

<!-- task\_rym\_x3p\_gpb -->

### Adding Code Values by Uploading a CSV File



<a name="task_rym_x3p_gpb__steps_tcj_1jp_gpb"/>

## Procedure

1.  On the *MIG Codelists* tab, choose *Create* to create a new codelist.

2.  Specify the codelist identifier, name, and definition in the corresponding fields under *MIG Codelists*.

3.  Choose *Code Values*.

4.  On the *Code Values* tab, choose *Upload* to import a CSV file containing code values.

5.  In the *Code Value Upload* dialog box, choose *Select*, and browse and upload the CSV file containing code values. You have the following options for uploading a file:

    -   If you already have a **CSV file**containing code values, choose <span class="SAP-icons-V5"></span> Browse or drop a file and select the file.

    -   You can **download a standard codelist** from a type system in CSV format and upload it here:

        1.  Go to *Type Systems* and open the required type system.
        2.  Go to the *Codelists* tab and select the version you want to download.
        3.  In the *Code Values* tab, choose *Download*.

    -   If you **don't have a CSV file** yet, in the *Code Value Upload* dialog, you can download a template by choosing *How to...* \> ** *Download the template \(\*.CSV\)*. The file is saved locally with the name `CodeValueDownload.csv`. Edit the downloaded template file `CodeValueDownload.csv` to enter the required values and save, but make sure not to change or remove the template header. Then, select the file in the upload dialog.

    -   You can use the upload option even if there are **already code values in the list**. In that case, the code values from the file are appended to the existing list.

        However, if there are **duplicate values** between the list and the CSV file, during the upload, a dialog displays the list of already existing values. Select the checkbox of the values that you want to overwrite and choose *Overwrite*.


6.  If the selected CSV file contains any code value with an escape character, the list of those code values is displayed when on uploading the file. Select the rows for which you want the escape character to be removed and choose *Remove*.

    To skip this step, choose *Skip All*.

7.  You can add more code values manually by choosing *Create* and entering the required fields.


