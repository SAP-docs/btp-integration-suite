<!-- loio9bd43c9ae064493286f321551bd0557c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Trading Partner Agreement

A trading partner agreement is an agreement of a contract defined by two trading parties that have decided to exchange certain business data or items using a B2B scenario for fullfilling the agreed trading/business process in a given business context.

Creating an agreement is the last step in the design of a B2B transaction and consists of tow trading partners representing one type of transaction between those two partners. Follow the procedure below to create a trading partner agreement.

1.  Log on to your Integration Suite .
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to *Agreements* tab and choose *Create*.

4.  This will display a list of agreement templates available in the system. Select the list <span class="SAP-icons"></span> button next to an agreement template you wish to use.
5.  The next screen displays the list of transactions available under the template. Select one or more transactions from the list for your agreement and choose *OK*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md)

6.  In the *Overview* tab, maintain the following fields under the *Details* section

    **Details**


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
    
    Name


    
    </td>
    <td valign="top">
    
    Name of the agreement


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description


    
    </td>
    <td valign="top">
    
    Provide a description of your agreement


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version


    
    </td>
    <td valign="top">
    
    Enter a version of your agreement


    
    </td>
    </tr>
    </table>
    
7.  Maintain the following fields under *My Company Details* section

    **My Company Details**


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
    
    System


    
    </td>
    <td valign="top">
    
    Select a system from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System


    
    </td>
    <td valign="top">
    
    Select a type system from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Contact Person

    This field appears only when you choose *GS1 XML* as the type system.


    
    </td>
    <td valign="top">
    
    Select a contact person from the drop-down list.

    > ### Note:  
    > You need to have the Business Expert to assign a contact person. To know more on assigning roles, see [Configuring User Access](../configuring-user-access-2c6214a.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System Version


    
    </td>
    <td valign="top">
    
    Select a type system version from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier


    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided. You can also create an identifier using the :heavy_plus_sign: button.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier as Trading Partner


    
    </td>
    <td valign="top">
    
    Select an identifier from your company that will be the trading partner. You can also create an identifier using the :heavy_plus_sign: button.


    
    </td>
    </tr>
    </table>
    
8.  Maintain the following fields under *Trading Partner Details* section

    **Trading Partner Details**


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
    
    Name


    
    </td>
    <td valign="top">
    
    Name of the trading partner


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    System


    
    </td>
    <td valign="top">
    
    Select a system from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System


    
    </td>
    <td valign="top">
    
    Select a type system from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Contact Person

    This field appears only when you choose *GS1 XML* as the type system.


    
    </td>
    <td valign="top">
    
    Select a contact person from the drop-down list.

    > ### Note:  
    > You need to have the Business Expert to assign a contact person. To know more on assigning roles, see [Configuring User Access](../configuring-user-access-2c6214a.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System Version


    
    </td>
    <td valign="top">
    
    Select a type system version from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier


    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided. You can also create an identifier using the :heavy_plus_sign: button.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier as Company


    
    </td>
    <td valign="top">
    
    Select an identifier from the trading partner for the company. You can also create an identifier using the :heavy_plus_sign: button.


    
    </td>
    </tr>
    </table>
    
9.  Choose *Save*. Once you save the agreement, the *Overview* tab also displays the *Purpose* of the type system you chose.
10. Navigate to the *B2B Scenarios* tab. This tab displays the transactions that are created under the agreement template.
11. Choose the *Communication Channel* step on the sender side.
12. Select a value from the drop-down list for the field *Communication*.
13. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

14. Select the *Interchange* step on the sender side.
15. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field. Once you choose a MIG, the message type used within that MIG is displayed under the *Message Type* field.

    > ### Note:  
    > -   Ensure you have the required MIG created in the Integration Advisor.
    > 
    > -   Trading Partner Management only supports the following type systems:
    >     -   Edifact
    > 
    >     -   X12
    >     -   SAP IDoc
    >     -   SAP SOAP On-Premise
    >     -   SAP SOAP Cloud
    >     -   GS1 XML

16. For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.
17. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

18. If you are planning to use custom integration flows for Pre-Processing and Post-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.
19. Provide the address of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

20. The *Enable Payload Validation* checkbox allows the system to validate the incoming payload. Check/Uncheck the option if you want to enable or disable the payload validation.
21. Choose the *Mapping* step on the sender side.
22. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

23. If you want to use custom integration flow for the Mapping process, enable the checkbox for *Customized Mapping Processing* and provide the address of the integration flow under the field *Process Direct Address* field.

    > ### Note:  
    > Enabling custom message processing will disable the *Mapping Guideline \(MAG\)* field.
    > 
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

24. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.
25. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

26. Select the *Interchange* shape on the receiver side.
27. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

28. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

29. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

30. Provide the address path of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

31. The *Enable Payload Validation* checkbox allows the system to validate the outgoing payload. It is selected by default. Uncheck the option if you want to disable the payload validation.
32. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12
    > 
    > 
    > You also need to maintain the Functional Acknowledgement in the Receiver side.

33. If you have enabled *Receiver Functional Acknowledgement*, choose *Communication* on the receiver side and set the following values:
    -   *Communication*: It should be of type AS2. This detail has to be maintained in the trading partner profile. To know more, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md)

    -   *Receiver Functional Acknowledgement Channel*: Select a value from the drop-down list

34. Choose *Parameters* if you want to add any paramaters to the template.
35. In the *Parameters* tab displayed, choose *Add Parameters*. This will display the following options:
    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. You can choose either *Request* or *Response* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile](creating-a-company-profile-909d928.md)

    -   *Extend from TP*: This option allows you to use the dynamic parameters from the trading partner profile used in the agreement template. You can choose either *Request* or *Response* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your own activity paramaters using this option. Select this option and choose *Request* or *Response*. Maintain the values of the fields *Parameter Key* and *Value* and choose *Create*.

36. Choose *Save*.

You have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Activating a Trading Partner Agreement](activating-a-trading-partner-agreement-baed0e3.md "Activate your trading partner agreement to push the agreement details into the SAP Cloud Integration partner directory.")

