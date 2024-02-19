<!-- loio6318fe606a8f44a88d6cc2255c06ee1e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating MIG Codelists

Create new Message Implementation Guideline \(MIG\) codelists if the reusable or type-system based codelists don’t meet your requirements.



<a name="loio6318fe606a8f44a88d6cc2255c06ee1e__prereq_e32_pzl_fpb"/>

## Prerequisites

You’ve opened the MIG in the edit mode.

<a name="task_ahs_bcp_gpb"/>

<!-- task\_ahs\_bcp\_gpb -->

## Creating MIG codelists by manually adding code values



<a name="task_ahs_bcp_gpb__steps_fxv_q2p_gpb"/>

## Procedure

1.  On the *MIG Codelists* tab, choose *Add* to create a new codelist.

2.  Specify the codelist identifier, name, and definition in the corresponding fields under *MIG Codelists*.

3.  Choose *CodeValues*.

4.  On the *Code Values* tab, in the resulting panel, choose *Add* to enter the required values.

5.  Optional: Filter code values using *Search*.

6.  Optional: Sort code values using <span class="SAP-icons-V5"></span> \(sort\) icon in ascending or descending order.

7.  Optional: Delete code values using :wastebasket: icon.

8.  Optional: Download the code values in **csv** format using the *Download* option. The dowloaded file will correspond to the csv template used for the codelist upload. This helps when you want to update the downloaded csv file and upload it again. Follow the procedure below to upload a csv file.


<a name="task_rym_x3p_gpb"/>

<!-- task\_rym\_x3p\_gpb -->

### Creating MIG codelists by uploading a csv file



<a name="task_rym_x3p_gpb__steps_tcj_1jp_gpb"/>

## Procedure

1.  On the *MIG Codelists* tab, choose *Add* to create a new codelist.

2.  Specify the codelist identifier, name, and definition in the corresponding fields under *MIG Codelists*.

3.  Choose *CodeValues*.

4.  On the *Code Values* tab, in the resulting panel, choose *Upload* to import the csv file containing code values.

    > ### Note:  
    > You can also download a standard codelist from a type system in `csv` format and upload it here. To do so,
    > 
    > -   Go to *Type Systems* and open the type system that you require.
    > 
    > -   Navigate to the *Codelists* tab and select a version of the codelist that you want to download.
    > -   In the *Code Values* tab, choose *Download*. This will download the standard codelist in `csv` format.

5.  In the *Code Value Upload* dialog box, choose *Select*, and browse and upload the csv file containing code values.

    > ### Note:  
    > If you do not have a csv file but need to enter the values in a file, in the *Code Value Upload* dialog, choose *How to* \> ** *Download the template* option. This will download the csv file template locally with the name `CodeValueDownload.csv`. Edit the downloaded template file `CodeValueDownload.csv` to enter the required values and save.
    > 
    > Ensure you do not change or remove the header of the template.
    > 
    > Once done, you can choose *Select* to upload the updated file containing code values.

6.  If the csv file contains any code value with an escape character, on uploading the file the list of those code values are displayed. Select the rows for which you want the escape character to be removed and choose *Remove*.

7.  If you want to skip this step, choose *Skip All*.

8.  If you want to add more code values to the uploaded values, choose *Add* and enter the required fields in the new entry.

    > ### Note:  
    > You can use the upload option even if code values exist already. The code values in the file get appended to the existing list. However, if there are conflicting values between the list and the csv file, during upload the dialog box displays the list of already existing values. You can select the checkbox of those values that you wish to overwrite and choose *Overwrite*.


