<!-- loio5f0518aa8b9b4ac8837c36fc8f0f20cb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating XSLT Mapping Guidelines

Learn how to create a new mapping guideline that uses an XSLT file as its source.



## Context

Besides the graphical mapping guidelines, which you define by drawing lines, you can also create XSLT mapping guidelines, which use XSLT files as source.



## Procedure

1.  Go to *Design* \> *MAGs*.

2.  Choose *Create* \> *XSLT MAG*.

3.  In the first step of the creation wizard, select a **source MIG**. Choose *Next*.

4.  Then, select a **target MIG** and choose *Next*.

5.  Finally, in the tab *MAG Creation*, enter a name for the new mapping guideline and choose *Create*. The new mapping guideline opens in edit mode, with unresolved errors due to a missing XSLT file.

6.  To add an XSLT file, go to the *Mapping Details* and choose *Browse*, next to *New XSLT File*.

7.  Select an XSLT file from your file system. To upload it to the MAG, choose *Save*.

    After saving, you can review the content of the XSLT file by choosing :eye: and you can download the file by choosing <span class="SAP-icons-V5"></span> Download XSLT File.

    To update the file, simply choose *Browse* again and upload a new file, thereby replacing and overwriting the previous file.

8.  Now, you can simulate the new MAG by choosing either *Simulate* \> *Simulate with MIG Example Data* or *Simulate* \> *Simulate with Payload Data*. After a successful simulation, you can download the simulation results by choosing <span class="SAP-icons-V5"></span> Download Simulation Results.

9.  Finally, to activate the MAG, return to display mode by choosing *Cancel*, then choose <span class="SAP-icons-V5"></span> Actions, followed by *Activate*. The version status switches to *Active*.




## Results

You've created a new XSLT mapping guideline and uploaded an XSLT file as its source.



## Next Steps

After activating a MAG, you can perform the following actions:

-   To edit a MAG after activating it, you have to create a new draft version of the MAG by choosing *Edit*. You can then upload a new XSLT file by choosing Browse in the *Mapping Details* section, and contuining as described previously.
-   Copy a mapping guideline: While your mapping guideline is in draft or active status, you can create a copy of it by choosing *Copy*. You can then attach an XSLT file to the new copy.

