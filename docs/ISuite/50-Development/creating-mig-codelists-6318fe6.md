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

6.  Optional: Sort code values using <span class="SAP-icons"></span> \(sort\) icon in ascending or descending order.

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

5.  In the *Code Value Upload* dialog, choose *How to* \> ** *Download the template* option.

6.  Edit the downloaded template file `CodeValueDownload.csv` to enter the required values and save.

    > ### Note:  
    > Please don't change or remove the header of the template.

7.  Choose *Select* to upload the updated file containing code values.

    > ### Note:  
    > You can use the upload option even if code values exist already. The code values in the file get appended to the existing list. However, you can handle conflicting values between the list and the csv file by choosing one of the following options:
    > 
    > -   Overwrite All - Choose this option to replace all the conflicting values of the list with the values of the uploaded file.
    > -   Interactive Overwrite - Choose this option to selectively overwrite the conflicting values of the list with the values of the uploaded file.


