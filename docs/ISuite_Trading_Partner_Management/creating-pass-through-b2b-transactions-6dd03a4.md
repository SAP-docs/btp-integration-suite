<!-- loio6dd03a45e6d74b63935a7ecef70932b1 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating Pass-Through B2B Transactions

Create a pass-through B2B transaction to set up a transaction with no additional configuration or processing. This is useful for forwarding data without any extra steps, making the process more efficient.



## Context

A pass-through B2B \(Business-to-Business\) transaction refers to a type of electronic data interchange \(EDI\) or business-to-business integration scenario where a company acts as an intermediary or a "pass-through" entity.

In a pass-through B2B transaction:

1.  Company A sends a business document \(for example, purchase order, invoice\) to Company B.
2.  Company B receives the document but doesn't process it internally. Instead, it forwards the document to Company C.
3.  Company C receives the document and processes it accordingly.

In this scenario, Company B acts as a pass-through entity, facilitating the exchange of business documents between Company A and Company C without modifying or processing the content. This type of transaction is commonly seen in industries like logistics, transportation, and supply chain management.



## Procedure

1.  Navigate to the *B2B Scenarios* tab and choose *Create Business Transaction*.

2.  In the *Create Business Transaction* dialog, maintain the following details:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Name**
    
    </td>
    <td valign="top">
    
    Provide a name for your business transaction.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Business Transaction Pattern**
    
    </td>
    <td valign="top">
    
    Define the interaction pattern for the business transaction.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Pass-Through**
    
    </td>
    <td valign="top">
    
    Select this checkbox if the transaction is a pass-through entity, requiring no additional configuration or processing beyond forwarding the data.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **My Company Role**
    
    </td>
    <td valign="top">
    
    Check the radio button based on whether your company is an *Initiator* or *Reactor*.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*. A new entry gets created.

4.  In the newly created transaction, choose the *Communication* step on the sender side.

5.  Select a value from the drop-down list for the field *Communication*.

6.  Select the *Interchange* step on the sender side.

7.  Edit the version numbers in the *Type System Version* field.

8.  To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md)

9.  Similarly, choose the *Communication Channel* on the receiver side and enter a value for the field *Communication*.

10. Select the *Interchange* shape on the receiver side.

11. Select the *Enable Receiver Functional Acknowledgement* checkbox if you want to enable the functional acknowledgment for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

    You can view the status of the Functional Acknowledgment through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md)

12. If the acknowledgment is partially accepted, you can choose how to label such acknowledgments in the field *Mark Partially Accepted Acknowledgement as* and choose one of the following options:

    1.  Interchange Failed

    2.  Interchange Completed


13. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

14. The *Mapping* step of the transaction does not require any configuration as this is a pass-through transaction.

15. Choose anywhere outside the transaction and the common properties get displayed below the transaction. Choose the *Activity Parameters* tab if you want to add any parameters to the template.

16. Choose *Add Parameters*. This displays the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. If you've created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Select a parameter from the list and choose *Save*.

        If you want to add dynamic parameters to a company profile, see [Creating a Company Profile and a Subsidiary](creating-a-company-profile-and-a-subsidiary-909d928.md).

    -   *Create Trading Partner Parameters*: This option allows you to create dynamic parameters for the trading partner profile used in the agreement template. If you've created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. A dialog box with the *Parameter Key* field is displayed. Enter a value for the field and choose *Save*.

        If you want to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md).

    -   *Create Activity Parameters*: You can also create your own activity parameters using this option. If you’ve created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.

17. Choose *Save*.




<a name="loio6dd03a45e6d74b63935a7ecef70932b1__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

