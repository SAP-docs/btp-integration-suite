<!-- loio72679dde3e5a499c9eb7863572c52ef3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating Agreement - Latest Format

Create agreements using the latest template format.



## Context

The new agreement template comprises of alias based configurations that help with maintaining information such as trading partner details and B2B transaction details directly in the agreement template. With this template, there could be situations where multiple trading partners have the same B2B scenarios defined. In such cases, if a change has to be done for a B2B scenario, you need to make individual changes in each of the agreement consisting of that scenario. To help avoid this, while creating an agreement, you can now choose to copy or reference the B2B scenarios from the template.

-   With Copy mode, the agreement that you create will have its own set of B2B scenarios\(replicated from the agreement template\) and you can edit and make changes to them.

-   With Reference mode, your agreement will only refer to the B2B scenarios that exist in the template. In this mode, the B2B scenarios are not editable in the agreement and they can be updated only by editing them in the actual agreement template. If you have multiple trading partners using the same B2B scenarios, then with Reference mode, you can make the changes only once in the referenced template and the changes will get updated in the agreements directly.

You can choose between these two modes at the time of agreement creation. The options provided are:

-   *Copy from Template*: This will copy the B2B scenarios from the template into your agreement and you can make changes to them directly in your agreement. The changes made to the B2B scenarios will be applicable only for that agreement.

-   *Bind with Template*: This will bind your agreement with the template by referencing the B2B scenarios available in the agreement template. So the newly created agreement will have B2B scenarios that are read-only. If you want to update the transactions, you can do so by editing them in their referencing template and the changes will be applied automatically to the referencing agreements.

> ### Note:  
> The *Bind with Template* mode does not apply for the templates with *Outdated Format*.

The creation modes apply only for the agreements you newly create. The agreements that were created in the past do not have the *Creation Mode* field displayed and can no longer be edited or copied. They have to be migrated to the latest format to continue editing. Follow the steps mentioned in [Migrating an Agreement](migrating-an-agreement-bdcf534.md) to migrate your old agreements to this new format.



## Procedure

1.  Log on to your application.

2.  Choose *Design* \> *B2B Scenarios*.

3.  Navigate to *Agreements* tab and choose *Create*.

4.  This will display a list of agreement templates available in the system. The templates with outdated format will have the label *Outdated Format* right after the name. Select a template without the label if you want to use the latest format for your agreement and choose *Next*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md).

5.  The next screen displays the *Agreement Creation Mode* with the following options:

    1.  *Copy from Template*: This will copy the B2B scenarios into your agreement from the template. You can edit the transactions in the agreement.

    2.  *Bind with Template*: This will bind you agreement with the template by creating a reference of the *B2B Scenarios* in the agreement. Here you cannot edit the transactions in the agreement. They can be edited only in the referenced agreement template and updated in the agreement.

        Select an option depending on your requirement.


6.  Under the *Transactions* table, select the transactions for your agreement.

7.  Select the trading partner from the drop-down list under *Select Trading Partner* section and choose *Open Draft*.

8.  If you have created this agreement from a template that has communication partner in it, you can see the relevant detail in the *Communication Partner* field in the *Trading Partner Details* section.

9.  The newly created agreement will have a field by name *Creation Mode*. This will display the mode that you chose for your agreement. If you chose to copy them into your agreement, it will display *Copied from Template*. If you chose to only reference the B2B scenarios, it will display *Bound with Template* and you can select *Refresh* button if you want to see any latest update on the B2B scenarios. A timestamp near this button displays the last update that was applied on the agreement.

10. If you have maintained the necessary alias information in the template, the corresponding trading partner details will get filled in automatically in the agreement. Steps number 10 to 13 are optional.

    > ### Note:  
    > As the new agreement template is alias-based, ensure you maintain the right alias across the system. Only then, the right trading partner configuration can be picked up using the alias when creating the agreement.

11. In the *Overview* tab, maintain the following fields under the *Details* section:

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
    
    Enter a version for your agreement
    
    </td>
    </tr>
    </table>
    
12. Maintain the following fields under *My Company Details* section:

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
    
13. Maintain the following fields under *Trading Partner Details* section. The *Name* of the trading partner is autofilled based on the value you chose in Step 6.

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
    
14. Choose *Save*.

15. Once you save the agreement, the field *Creation Mode*is displayed showing the creation mode that you chose for your agreement. It will display *Copied from Template* if you had chosen to copy the template into your agreement.

    If you chose to only reference the B2B scenarios, it will display *Bound with Template* and you can select *Refresh* button if you want to see any latest update on the B2B scenarios. A timestamp near this button displays the last update that was applied on the agreement.

    The *Trading Partner Details* section also displays the *Purpose* of the type system you chose.

16. Navigate to the *B2B Scenarios* tab. This tab displays the transactions that you chose from the agreement template. Choose *Edit* to start working with the transactions.

    > ### Remember:  
    > The *Edit* option is available only if you chose *Copy from Template* at the time of agreement creation. For referenced B2B scenarios, you can only view them in this tab.
    > 
    > Steps 12 to 35 are optional if you have the template filled with the necessary alias information. With the new template, you can configure all the steps of the transaction including the *Mapping* step.

17. Choose the *Communication Channel* step on the sender side.

18. Select a value from the drop-down list for the field *Communication*.

19. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).

20. Select the *Interchange* step on the sender side.

21. Set the target decimal value of the incoming payload in the *Target Decimal Character* field.

    > ### Note:  
    > This field appears only for **UN/EDIFACT** type system.

22. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

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

23. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).

24. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox for the field *Customized Pre-Processing*.

25. Provide the address of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

26. The *Enable Payload Validation* checkbox allows the system to validate the incoming payload. Check/Uncheck the option if you want to enable or disable the payload validation.

    If enabled, the generic integration flow will perform a validation check for the sender interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.

27. The *Enable Syntax Validation* checkbox allows the system to validate the syntax using EDI splitter and this option is selected by default. Check/Uncheck the option if you want to enable or disable the syntax validation.

    > ### Note:  
    > This option applies only to the following sender type systems:
    > 
    > -   ASC X12
    > 
    > -   UN/EDIFACT
    > 
    > If the identifier used in the agreement has **Custom Scheme Code**, then this option will be skipped irrespective of the field selection.
    > 
    > This option is not editable if you have created the agreement with reference mode \(created using *Bind with Template* option\).

28. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

29. Choose the *Mapping* step.

30. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

31. If you want to use custom integration flow for the Mapping process, enable the checkbox for *Customized Mapping Processing* and provide the address of the integration flow under the field *Process Direct Address* field.

    > ### Note:  
    > Enabling custom message processing will disable the *Mapping Guideline \(MAG\)* field.
    > 
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

32. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.

33. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).

34. Select the *Interchange* shape on the receiver side.

35. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

36. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

37. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

38. Provide the address path of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

39. The *Enable Payload Validation* checkbox allows the system to validate the outgoing payload. It is selected by default. Uncheck the option if you want to disable the payload validation.

    If enabled, the generic integration flow will perform a validation check for the receiver interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.

40. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

41. If you want to use custom seperators for your payload, enable the *Use Custom Seperators* checkbox and maintain the values for the following fields:

    > ### Note:  
    > This option is available only for UN/EDIFACT and ASC X12 type systems.

    -   Segment Terminator

    -   Composite Seperator
    -   Data Element Seperator
    -   Escape Character

42. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12
    > 
    > 
    > You also need to maintain the Functional Acknowledgement in the Receiver side.

43. If you have enabled *Receiver Functional Acknowledgement*, choose *Communication* on the receiver side and set the following values:

    1.  *Communication*: It should be of type AS2. This detail has to be maintained in the trading partner profile. To know more, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md).

    2.  *Receiver Functional Acknowledgement Channel*: Select a value from the drop-down list.


44. If you want to specify which separators to be used in the interchange message payload, select the checkbox for the field *Use Custom Separators*. This will enable the following fields. Set the character from the drop-down list for each of the separator.

    -   *Segment Terminator*

    -   *Composite Separator*
    -   *Data Element Separator*
    -   *Escape Character*

    > ### Note:  
    > You can also manually specify the custom separator for these fields. Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use **\+** as the separator.

45. Choose *Save*.

46. For further configuration, see:

    1.  [Adding Activity Parameters](adding-activity-parameters-655a594.md)

    2.  [Adding Custom Search Attributes](adding-custom-search-attributes-934bbcd.md)


47. 48. You have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

    1.  Created By

    2.  Created Date

    3.  Last Modified By

    4.  Modified Date



