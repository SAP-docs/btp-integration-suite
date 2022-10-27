<!-- loio8b7eb45224cb4162917ec7f5958d9c29 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding a Custom Message



## Context

You can add a custom message to a custom type system library.



## Procedure

1.  Navigate to the *Custom Type Systems* <span class="SAP-icons"></span> from the left pane of your application.

2.  Choose and open the custom type system and navigate to the *Messages* tab.

3.  This tab displays the list of uploaded custom messages. Choose *Add* to upload a custom message.

4.  Choose *Browse* and upload the XSD file under the *XSD File* step.

    > ### Note:  
    > The maximum file size that you can upload is 10MB, with a maximum limit of 20000 nodes.

5.  The next step shows you all the messages present in your XSD. Choose the required message from the *Messages* step.

6.  The details of the message will be auto-filled under the *Message Creation*step. You can verify and modify the details.

    > ### Note:  
    > -   The fields *Identifier* and *Version* uniquely identifies your message.
    > 
    > -   You can create multiple versions for a message with the same *Identifier*.
    > -   If you upload a message with already existing *Identifier* and *Version*, a new *Revision* of the message gets created. And, only the latest revision of the message gets displayed in the *Messages* list.

7.  Choose *Create*.




<a name="loio8b7eb45224cb4162917ec7f5958d9c29__result_azq_21h_spb"/>

## Results

The custom message is now successfully imported into the system.

