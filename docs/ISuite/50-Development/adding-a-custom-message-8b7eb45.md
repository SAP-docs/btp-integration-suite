<!-- loio8b7eb45224cb4162917ec7f5958d9c29 -->

# Adding a Custom Message



## Context

You can add a custom message to a custom type system library.



## Procedure

1.  Go to *Design* \> *Custom Type Systems*.

2.  Choose and open the custom type system and navigate to the *Messages* tab. This tab displays the list of uploaded custom messages.

3.  To upload a custom message, choose *Create* or *Create* \> *Custom Message*. A wizard opens.

4.  In the *XSD File*/*WSDL File* step, choose *Browse* and upload the XSD/WSDL file.

    > ### Note:  
    > The following applies:
    > 
    > -   XSD files are intended for XML and IDoc custom type systems and WSDL files for SOA type system.
    > 
    > -   The maximum file size that you can upload is 10 MB, with a maximum limit of 20000 nodes.
    > 
    > -   Uploading custom IDocs requires an XSD in the format as downloaded from the Enterprise Service Repository \(ESR\) or from the transaction *WE60* of your SAP S/4HANA backend system.

5.  The next step shows you all the messages present in your XSD/WSDL. Choose the required message from the *Messages* step.

6.  The details of the message are auto-filled under the *Message Creation* step. You can verify and modify the details.

    > ### Note:  
    > -   The fields *Identifier*, *Namespace* and *Version* uniquely identify your message.
    > 
    > -   You can create multiple versions for a message with the same *Identifier* and *Namespace*.
    > -   If you upload a message with already existing *Identifier*, *Namespace* and *Version*, a new *Revision* of the message gets created. And, only the latest revision of the message gets displayed in the *Messages* list.

7.  For custom IDoc creation, the *Message Creation* step displays the following additional fields:

    1.  *Message Type*: This is a mandatory field which is auto-filled by the proposals picked from the xsd file. If not, you need to enter a meaningful text.

    2.  *IDoc Type*: This is a mandatory field which is auto-filled by the proposals picked from the xsd file. If not, you need to enter a meaningful text.

    3.  *Extension Type*: This is an optional field which is auto-filled by the proposals picked from the xsd file.


    The *Identifier* field is read-only and auto-populated using the values provided in the previous fields. The format is as follows: **Message Type.IDoc Type.Extension Type**.

    > ### Example:  
    > For the following values, the *Identifier* field is populated as **INVOIC.INVOIC02.ZINVOIC02**:
    > 
    > -   *Message Type*: `INVOIC`
    > -   *IDoc Type*: `INVOIC02`
    > -   *Extension Type*: `ZINVOIC02`

    > ### Note:  
    > Newly created custom IDoc message types \(or message type versions\) automatically include an additional hierarchy level called *IDOC* below the root node. You can set this node to repeating in your MIG and model bulk IDocs in Integration Advisor.

8.  Choose *Create*.




<a name="loio8b7eb45224cb4162917ec7f5958d9c29__result_azq_21h_spb"/>

## Results

The custom message is imported into the system.

<a name="concept_clb_1t5_czb"/>

<!-- concept\_clb\_1t5\_czb -->

## Extend Standard Message for Custom IDoc

For custom IDocs type systems, the *Create* button also has the option *Extended Standard Message*. With this option you can upload an IDoc message using an XSD file and then reference that message to a standard IDoc. Standard IDocs contain an enriched structural definition such as codelists, qualifiers, long-text documentation and DateTime information. The custom IDoc xsd files \(as downloaded from transaction WE60 of your SAP S/4HANA backend system\) that you upload don't carry this additional information attached to these segment definitions. Now, with this option, these details \(codelists, qualifiers, long-text documentation and DateTime information\) are copied from the referenced standard IDoc to the custom IDoc.

> ### Note:  
> This additional information can only be copied for the standard segments \(from the standard IDoc\). Custom segments cannot be enriched using this option. For custom segments, you can manually enrich the MIG.

To add an extended standard message, complete the following steps:

1.  Choose *Create* \> *Extended Standard Message*.

2.  Choose *Browse* and upload the XSD file under the *XSD File* step.
3.  The next step shows you all the messages present in your XSD. Choose the required message from the *Messages* step.
4.  In the *Standard Type System* step, select the type system from which you want to choose the standard message.
5.  The *Standard Message* step displays the list of IDoc messages available in the selected type system. Select the required message from the list.
6.  The next step, *Standard Versions*, shows the list of versions available for the message that you chose. Select the version that you need to refer to your custom IDoc.
7.  The next step gives an overview of your selection. You can view a consolidated list of the standard message that you chose. Select *Create*.
8.  Select and open the newly created custom IDoc. You can now see the standard segments enriched with additional information.

