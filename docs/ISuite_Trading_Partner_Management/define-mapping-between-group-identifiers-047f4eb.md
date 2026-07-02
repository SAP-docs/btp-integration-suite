<!-- loio047f4eb947234f46b10f9fc825448ff9 -->

# Define Mapping between Group Identifiers

Define your custom integration flow to establish mapping between group identifiers.



## Context

For agreements containing single identifiers between partners, the mapping is one to one and is already established. In scenarios, where group identifiers are used in agreements, a mapping has to be defined in order to connect the individual identifiers present in the identifier groups of the partners. You can achieve this using your custom integration flow. To know more, follow the procedure below:



## Procedure

1.  Open the agreement that has group identifers defined in it and navigate to the *B2B Scenarios* tab.

2.  Choose *Edit*.

3.  In the corresponding transaction, select the *Interchange* step on the receiver side.

4.  Select the checkbox for the field *Customized Post-Processing* and provide an address in the *Process Direct Address* field.

5.  For the custom integration flow, create an integration flow with Process Direct adapter for the sender adapter and provide the same address in the *Address* field for the adapter.

6.  In the integration flow, create a groovy script with correct headers to maintain the mapping. The following camel headers can be used in the cutom integration flow:

    Ensure that all the headers start with term **SAP\_**.


    <table>
    <tr>
    <th valign="top">

    Header
    
    </th>
    <th valign="top">

    Definition
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **SAP\_EDI\_Sender\_ID**
    
    </td>
    <td valign="top">
    
    Represents the single sender identifier on the inbound.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **SAP\_EDI\_Receiver\_ID**
    
    </td>
    <td valign="top">
    
    Represents the single receiver identifier on the inbound.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **SAP\_TPM\_REC\_Sender\_ID**
    
    </td>
    <td valign="top">
    
    This is a newly introduced header. It can be used to represent the single sender identifier on the outbound. It will be applied to outbound payload and B2B Monitor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **SAP\_TPM\_REC\_Sender\_Name**
    
    </td>
    <td valign="top">
    
    This is a newly introduced header. It represents the sub organization name for sender, if sender identifier in the inbound is configured as Group Identifier. It will be applied to B2B Monitor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **SAP\_TPM\_REC\_Receiver\_Name**
    
    </td>
    <td valign="top">
    
    This is a newly introduced header. It represents the sub organization name for receiver, if receiver identifier in the outbound is configured as Group Identifier. It will be applied to B2B Monitor.
    
    </td>
    </tr>
    </table>
    
7.  In the *Runtime Configuration* of your integration flow, enter the value `SAP_.*` for the field *Allowed Headers* field.


