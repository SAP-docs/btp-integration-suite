<!-- loio6949c3f90d0c4056a75b3059ce857d34 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Deleting Message Implementation Guidelines

This topic explains the different options available to delete a Message Implementation Guideline \(MIG\) that is no longer required.

You can choose to delete a MIG including its draft, active, or deprecated versions or only a specific version. You can also mass delete message implementation guidelines.

> ### Caution:  
> Deleting MIGs is permanent and can’t be undone.



<a name="loio6949c3f90d0c4056a75b3059ce857d34__section_qpx_1zn_p4b"/>

## Delete MIGs Including Draft, Active, or Deprecated Versions

1.  On the *Message Implementation Guidelines* screen, choose <span class="SAP-icons-V5"></span> More Options on the MIG that you want to delete and then choose *Delete*.

2.  In the *Delete Message Implementation Guideline* dialog box, choose *Delete complete Message Implementation Guideline \(including history\)*.




<a name="loio6949c3f90d0c4056a75b3059ce857d34__section_whn_114_p4b"/>

## Delete Specific Versions of MIGs



### Using the Message Implementation Guidelines Screen

1.  On the *Message Implementation Guidelines* screen, choose <span class="SAP-icons-V5"></span> More Options on the MIG that you want to delete and then choose *Delete*.

2.  In the *Delete Message Implementation Guideline* dialog box, choose *Delete this \(latest\) version*.




### Using the Overview Tab

1.  On the *Message Implementation Guidelines* screen, choose the specific version of the MIG that you want to delete.

2.  On the *Overview* tab, depending on the screen size, choose *Delete*, or choose <span class="SAP-icons-V5"></span> More and then choose *Delete*.

3.  In the *Confirm* dialog box, choose *OK*.

    > ### Note:  
    > You can't delete active MIGs.




### Using the History Link

1.  On the *Message Implementation Guidelines* screen, choose *History* on the MIG that you want to delete.

2.  From the *Message Implementation Guideline History Versions* table, choose <span class="SAP-icons-V5"></span> Actions on the version that you want to delete.

3.  In the *Confirm* dialog, choose *OK*.

    > ### Note:  
    > You can't delete active MIGs.




## Mass Delete Message Implementation Guidelines

To delete multiple message implementation guidelines at once, perform the following steps.

1.  Go to *Design* \> *MIGs* and choose *Mass Delete MIGs*.
2.  In the upcoming dialog, select the message implementation guidelines that you want to delete.

    Use the search and filters to narrow down the list of artifacts and then use the checkbox in the table header to only select those artifacts. For more information on the filter, see [Filtering MIGs](message-implementation-guidelines-migs-f9f2bab.md#loiof9f2bab3ff3a4d86863199f6531ee695__section_ejb_gxt_d4b).

    Choose *Next*.

    > ### Note:  
    > Message implementation guidelines can only be deleted if they're not referenced by any other artifacts.

3.  In the *Confirm Selection* step, check that you've selected the relevant message implementation guidelines and versions. If you're satisfied, delete them by choosing *Confirm Deletion*.
4.  In the *Results* screen, you can see the progress of the deletion. Once the deletion is finished, you can download a results file that contains the details of the deleted message implementation guidelines by choosing <span class="SAP-icons-V5"></span> Download.

