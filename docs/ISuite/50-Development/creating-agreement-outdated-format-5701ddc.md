<!-- loio5701ddcc2d8d4a4094618f7ccdc999f6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating Agreement - Outdated Format

Create a Trading Partner Agreement using the outdated format.



## Context

You are creating an agreement using the outdated template format. This template does not contain the latest features such as alias-based configuration, creation modes etc. To utilize these features, it is recommended to use the latest format. Agreement templates that are outdated will have the *Outdated Format* label next to their name.



## Procedure

1.  Log on to your application.

2.  Choose *Design* \> *B2B Scenarios*.

3.  Navigate to *Agreements* tab and choose *Create*.

4.  This will display a list of agreement templates available in the system. The templates with outdated format will have the label *Outdated Format* right after the name. Select the template that you want to use for your agreement and choose *Next*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md).

5.  The next screen displays the creation mode with *Copy from Template* selected by default. This is because the referencing option is not applicable for the templates with outdated format. The *Transactions* table provides a list of transactions available under the template. Select one or more transactions from the list for your agreement.

6.  Select the trading partner from the drop-down list under *Select Trading Partner* section and choose *Open Draft*.

7.  In the *Overview* tab, maintain the following fields under the *Details* section:


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
    
    Enter a version for your agreement
    
    </td>
    </tr>
    </table>
    
8.  Maintain the following fields under *My Company Details* section:

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
    > You need to have the Business Expert to assign a contact person. To know more on assigning roles, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).


    
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
    
    Identifier in Company Type System
    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided. You can also create an identifier using the :heavy_plus_sign: button.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier as Trading Partner Type System
    
    </td>
    <td valign="top">
    
    Select an identifier from your company that will be the trading partner. This field can be set only after defining the *Type System* field of the trading partner. You can also create an identifier using the :heavy_plus_sign: button.
    
    </td>
    </tr>
    </table>
    
9.  Maintain the following fields under *Trading Partner Details* section. The *Name* of the trading partner is autofilled based on the value you chose in Step 6:

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
    > You need to have the Business Expert to assign a contact person. To know more on assigning roles, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).


    
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
    
    Identifier in Trading Partner Type System
    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided. You can also create an identifier using the :heavy_plus_sign: button.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier in Company Type System
    
    </td>
    <td valign="top">
    
    Select an identifier from the trading partner for the company. You can also create an identifier using the :heavy_plus_sign: button.
    
    </td>
    </tr>
    </table>
    
10. Choose *Save*. Once you save the agreement, the *Overview* tab also displays the *Purpose* of the type system you chose.

11. Navigate to the *B2B Scenarios* tab. This tab displays the transactions that you chose from the agreement template. Choose *Edit* to start working with the transactions.

12. Choose the *Communication Channel* step on the sender side.

13. Select a value from the drop-down list for the field *Communication*.

14. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).

15. Select the *Interchange* step on the sender side.

16. Set the target decimal value of the incoming payload in the *Target Decimal Character* field.

    > ### Note:  
    > This field appears only for **UN/EDIFACT** type system.

17. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

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
    >     -   Tradacoms
    > 
    >         Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*
    > 
    > 
    > -   For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.

18. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitor Interchanges](monitor-interchanges-42c1199.md).

19. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox for the field *Customized Pre-Processing*.

20. Provide the address of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

21. The *Enable Payload Validation* checkbox allows the system to validate the incoming payload. Check/Uncheck the option if you want to enable or disable the payload validation.

    If enabled, the generic integration flow will perform a validation check for the sender interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.

22. The *Enable Syntax Validation* checkbox allows the system to validate the syntax using EDI splitter and this option is selected by default. Check/Uncheck the option if you want to enable or disable the syntax validation.

    > ### Note:  
    > This option applies only to the following sender type systems:
    > 
    > -   ASC X12
    > 
    > -   UN/EDIFACT
    > 
    > If the identifier used in the agreement has **Custom Scheme Code**, then this option will be skipped irrespective of the field selection.

23. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

24. Choose the *Mapping* step.

25. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

26. If you want to use custom integration flow for the Mapping process, enable the checkbox for *Customized Mapping Processing* and provide the address of the integration flow under the field *Process Direct Address* field.

    > ### Note:  
    > Enabling custom message processing will disable the *Mapping Guideline \(MAG\)* field.
    > 
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

27. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.

28. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).

29. Select the *Interchange* shape on the receiver side.

30. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

31. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

32. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

33. Provide the address path of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

34. The *Enable Payload Validation* checkbox allows the system to validate the outgoing payload. It is selected by default. Uncheck the option if you want to disable the payload validation.

    If enabled, the generic integration flow will perform a validation check for the receiver interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.

35. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

36. If your receiver type system is UN/EDIFACT, you might want to set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.

37. If you want to use custom seperators for your payload, enable the *Use Custom Seperators* checkbox and maintain the values for the following fields:

    > ### Note:  
    > This option is available only for UN/EDIFACT and ASC X12 type systems.

    -   Segment Terminator

    -   Composite Seperator
    -   Data Element Seperator
    -   Escape Character

38. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12
    > 
    > 
    > You also need to maintain the Functional Acknowledgement in the Receiver side.

39. If you have enabled *Receiver Functional Acknowledgement*, choose *Communication* on the receiver side and set the following values:

    -   *Communication*: It should be of type AS2. This detail has to be maintained in the trading partner profile. To know more, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md).

    -   *Receiver Functional Acknowledgement Channel*: Select a value from the drop-down list.

40. If you want to specify which separators to be used in the interchange message payload, select the checkbox for the field *Use Custom Separators*. This will enable the following fields. Set the character from the drop-down list for each of the separator.

    -   *Segment Terminator*

    -   *Composite Separator*
    -   *Data Element Separator*
    -   *Escape Character*

    > ### Note:  
    > You can also manually specify the custom separator for these fields. Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use **\+** as the separator.

41. Choose *Save*.

    > ### Note:  
    > Once saved, the agreement will be rendered read-only. To make further changes, migrate to the latest format. To know more, see [Migrating an Agreement](migrating-an-agreement-bdcf534.md).

42. For further configuration, see:

    1.  [Adding Activity Parameters](adding-activity-parameters-655a594.md)

    2.  [Adding Custom Search Attributes](adding-custom-search-attributes-934bbcd.md)


43. You have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

    1.  Created By

    2.  Created Date

    3.  Last Modified By

    4.  Modified Date



