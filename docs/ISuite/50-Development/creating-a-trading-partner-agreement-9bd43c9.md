<!-- loio9bd43c9ae064493286f321551bd0557c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Trading Partner Agreement

A trading partner agreement is an agreement of a contract defined by two trading parties that have decided to exchange certain business data or items using a B2B scenario for fullfilling the agreed trading/business process in a given business context.

Creating an agreement is the last step in the design of a B2B transaction and consists of two trading partners representing one type of transaction between those two partners. Follow the following procedure to create a trading partner agreement.

The trading partner agreement is created out of a predefined template. There has been an update on the template format and, both the old and updated templates are available for creating an agreement. The procedure varies for both the templates and the corresponding steps are provided in the respective sections.

> ### Note:  
> The sections *Activity Parameters* and *Custom Search Attributes* in this chapter are common to both the template formats.

*Agreement Creation Mode*

The new agreement template comprises of alias based configurations that help with maintaining information such as trading partner details and B2B transaction details directly in the agreement template. With this template, there could be situations where multiple trading partners have the same B2B scenarios defined. In such cases, if a change has to be done for a B2B scenario, you need to make individual changes in each of the agreement consisting of that scenario. To help avoid this, while creating an agreement, you can now choose to copy or reference the B2B scenarios from the template. With *Copy* mode, the agreement that you create will have its own set of B2B scenarios\(replicated from the agreement template\) and you can edit and make changes to them. With *Reference* mode, your agreement will only refer to the B2B scenarios that exist in the template. In this mode, the B2B scenarios are not editable in the agreement and they can be updated only by editing them in the actual agreement template. If you have multiple trading partners using the same B2B scenarios, then with *Reference* mode, you can make the changes only once in the referenced template and the changes will get updated in the agreements directly.

You can choose between these two modes at the time of agreement creation. The options provided are:

-   *Copy from Template*: This will copy the B2B scenarios from the template into your agreement and you can make changes to them directly in your agreement. The changes made to the B2B scenarios will be applicable only for that agreement.

-   *Bind with Template*: This will bind your agreement with the template by referencing the B2B scenarios available in the agreement template. So the newly created agreement will have B2B scenarios that are read-only. If you want to update the transactions, you can do so by editing them in their referencing template and the changes will be applied automatically to the referencing agreements.

> ### Note:  
> The *Bind with Template* mode does not apply for the templates with *Outdated Format*.

The creation modes apply only for the agreements you newly create. The agreements that were created in the past do not have the *Creation Mode* field displayed and can no longer be edited or copied. They have to be migrated to the latest format to continue editing. Follow the steps mentioned in [Migrating an Agreement](migrating-an-agreement-bdcf534.md) to migrate your old agreements to this new format.



<a name="loio9bd43c9ae064493286f321551bd0557c__section_jwz_dlj_lzb"/>

## Create Agreement - Outdated Format

1.  Log on to your application.
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to *Agreements* tab and choose *Create*.

4.  This will display a list of agreement templates available in the system. The templates with outdated format will have the label *Outdated Format* right after the name. Select the template that you want to use for your agreement and choose *Next*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md)

5.  The next screen displays the creation mode with *Copy from Template* selected by default. This is because the referencing option is not applicable for the templates with outdated format. The *Transactions* table provides a list of transactions available under the template. Select one or more transactions from the list for your agreement.
6.  Select the trading partner from the drop-down list under *Select Trading Partner* section and choose *Open Draft*.
7.  In the *Overview* tab, maintain the following fields under the *Details* section

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
    
8.  Maintain the following fields under *My Company Details* section.

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
    
9.  Maintain the following fields under *Trading Partner Details* section. The *Name* of the trading partner is autofilled based on the value you chose in step 6.

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
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

15. Select the *Interchange* step on the sender side.
16. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

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

17. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

18. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox for the field *Customized Pre-Processing*.
19. Provide the address of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

20. The *Enable Payload Validation* checkbox allows the system to validate the incoming payload. Check/Uncheck the option if you want to enable or disable the payload validation.
21. The *Enable Syntax Validation* checkbox allows the system to validate the syntax using EDI splitter and this option is selected by default. Check/Uncheck the option if you want to enable or disable the syntax validation.

    > ### Note:  
    > This option applies only to the following sender type systems:
    > 
    > -   ASC X12
    > 
    > -   UN/EDIFACT

22. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:8" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9bd43c9ae064493286f321551bd0557c.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .
23. Choose the *Mapping* step.
24. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

25. If you want to use custom integration flow for the Mapping process, enable the checkbox for *Customized Mapping Processing* and provide the address of the integration flow under the field *Process Direct Address* field.

    > ### Note:  
    > Enabling custom message processing will disable the *Mapping Guideline \(MAG\)* field.
    > 
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

26. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.
27. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

28. Select the *Interchange* shape on the receiver side.
29. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

30. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

31. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

32. Provide the address path of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

33. The *Enable Payload Validation* checkbox allows the system to validate the outgoing payload. It is selected by default. Uncheck the option if you want to disable the payload validation.
34. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:14" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9bd43c9ae064493286f321551bd0557c.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .
35. If your receiver type system is UN/EDIFACT, you might want to set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.
36. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12
    > 
    > 
    > You also need to maintain the Functional Acknowledgement in the Receiver side.

37. If you have enabled *Receiver Functional Acknowledgement*, choose *Communication* on the receiver side and set the following values:
    -   *Communication*: It should be of type AS2. This detail has to be maintained in the trading partner profile. To know more, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md)

    -   *Receiver Functional Acknowledgement Channel*: Select a value from the drop-down list

38. If you want to specify which separators to be used in the interchange message payload, select the checkbox for the field *Use Custom Separators*. This will enable the following fields. Set the character from the drop-down list for each of the separator.

    -   *Segment Terminator*

    -   *Composite Separator*
    -   *Data Element Separator*
    -   *Escape Character*

    > ### Note:  
    > You can also manually specify the custom separator for these fields. Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use **\+** as the separator.

39. Choose *Save*.



<a name="loio9bd43c9ae064493286f321551bd0557c__section_hvf_hlj_lzb"/>

## Create Agreement - Latest Format

1.  Log on to your application.
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to *Agreements* tab and choose *Create*.

4.  This will display a list of agreement templates available in the system. The templates with outdated format will have the label *Outdated Format* right after the name. Select a template without the label if you want to use the latest format for your agreement and choose *Next*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md)

5.  The next screen displays the *Agreement Creation Mode* with the following options:

    -   *Copy from Template*: This will copy the B2B scenarios into your agreement from the template. You can edit the transactions in the agreement.

    -   *Bind with Template*: This will bind you agreement with the template by creating a reference of the *B2B Scenarios* in the agreement. Here you cannot edit the transactions in the agreement. They can be edited only in the referenced agreement template and updated in the agreement.

    Select an option depending on your requirement.

6.  Under the *Transactions* table, select the transactions for your agreement.

7.  Select the trading partner from the drop-down list under *Select Trading Partner* section and choose *Open Draft*.
8.  The newly created agreement will have a field by name *Creation Mode*. This will display the mode that you chose for your agreement. If you chose to copy them into your agreement, it will display *Copied from Template*. If you chose to only reference the B2B scenarios, it will display *Bound with Template* and you can select *Refresh* button if you want to see any latest update on the B2B scenarios. A timestamp near this button displays the last update that was applied on the agreement.
9.  If you have maintained the necessary alias information in the template, the corresponding trading partner details will get filled in automatically in the agreement. Steps number 10 to 13 are optional.

    > ### Note:  
    > As the new agreement template is alias-based, ensure you maintain the right alias across the system. Only then, the right trading partner configuration can be picked up using the alias when creating the agreement.

10. In the *Overview* tab, maintain the following fields under the *Details* section

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
    
11. Maintain the following fields under *My Company Details* section.

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
    
12. Maintain the following fields under *Trading Partner Details* section. The *Name* of the trading partner is autofilled based on the value you chose in step 6.

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
    
13. Choose *Save*. Once you save the agreement, the *Overview* tab also displays the *Purpose* of the type system you chose.
14. Navigate to the *B2B Scenarios* tab. This tab displays the transactions that you chose from the agreement template. Choose *Edit* to start working with the transactions.

    > ### Remember:  
    > The *Edit* option is available only if you chose *Copy from Template* at the time of agreement creation. For referenced B2B scenarios, you can only view them in this tab.
    > 
    > Steps 12 to 35 are optional if you have the template filled with the necessary alias information. With the new template, you can configure all the steps of the transaction including the *Mapping* step.

15. Choose the *Communication Channel* step on the sender side.
16. Select a value from the drop-down list for the field *Communication*.
17. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

18. Select the *Interchange* step on the sender side.
19. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

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

20. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

21. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox for the field *Customized Pre-Processing*.
22. Provide the address of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

23. The *Enable Payload Validation* checkbox allows the system to validate the incoming payload. Check/Uncheck the option if you want to enable or disable the payload validation.
24. The *Enable Syntax Validation* checkbox allows the system to validate the syntax using EDI splitter and this option is selected by default. Check/Uncheck the option if you want to enable or disable the syntax validation.

    > ### Note:  
    > This option applies only to the following sender type systems:
    > 
    > -   ASC X12
    > 
    > -   UN/EDIFACT
    > 
    > This option is not editable if you have created the agreement with reference mode \(created using *Bind with Template* option\).

25. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:22" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9bd43c9ae064493286f321551bd0557c.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 
26. Choose the *Mapping* step.
27. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

28. If you want to use custom integration flow for the Mapping process, enable the checkbox for *Customized Mapping Processing* and provide the address of the integration flow under the field *Process Direct Address* field.

    > ### Note:  
    > Enabling custom message processing will disable the *Mapping Guideline \(MAG\)* field.
    > 
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

29. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.
30. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

31. Select the *Interchange* shape on the receiver side.
32. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

33. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

34. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

    > ### Note:  
    > The application now provides you with the *ProcessDirect* adapter that allows you to use your customised integration flow within the generic integration flow. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

35. Provide the address path of your custom integration flow in the *Process Direct Address* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

36. The *Enable Payload Validation* checkbox allows the system to validate the outgoing payload. It is selected by default. Uncheck the option if you want to disable the payload validation.
37. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:28" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9bd43c9ae064493286f321551bd0557c.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 
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
    -   *Communication*: It should be of type AS2. This detail has to be maintained in the trading partner profile. To know more, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md)

    -   *Receiver Functional Acknowledgement Channel*: Select a value from the drop-down list

40. If you want to specify which separators to be used in the interchange message payload, select the checkbox for the field *Use Custom Separators*. This will enable the following fields. Set the character from the drop-down list for each of the separator.

    -   *Segment Terminator*

    -   *Composite Separator*
    -   *Data Element Separator*
    -   *Escape Character*

    > ### Note:  
    > You can also manually specify the custom separator for these fields. Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use **\+** as the separator.

41. Choose *Save*.



<a name="loio9bd43c9ae064493286f321551bd0557c__section_dbw_ntb_bzb"/>

## Activity Parameters

If you want to add any activity parameters to your transaction, select anywhere outside the transaction flow to view the generic tabs and select the *Activity Parameters* tab

1.  Choose *Add Parameters*. This will display the following options:
    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. You can choose either *Inbound* or *Outbound* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile](creating-a-company-profile-909d928.md)

    -   *Extend from TP*: This option allows you to use the dynamic parameters from the trading partner profile used in the agreement template. You can choose either *Inbound* or *Outbound* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your own activity paramaters using this option. Select this option and choose *Inbound* or *Outbound*. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.




<a name="loio9bd43c9ae064493286f321551bd0557c__custom_search_attribute"/>

## Custom Search Attributes

If you want to add custom search attributes to the transaction,

1.  Navigate to the *Custom Search Attributes* tab and choose *Add*.

    > ### Note:  
    > To know how to create a custom search attribute, see [Configuration Manager](configuration-manager-7daf06c.md).

2.  In the resulting dialog, maintain the following fields:

    **Custom Search Attribute**


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
    
    Select a value from the list of attributes that you have created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Type
    
    </td>
    <td valign="top">
    
    Select whether your source is of type *Parameter* or *XPath*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Value
    
    </td>
    <td valign="top">
    
    Enter the source value for the name. If you chose *Source Type* as *Parameter*, you need to enter the parameter here. If you chose *XPath*, then you need to enter the xpath of the source value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Source
    
    </td>
    <td valign="top">
    
    Select whether you want the data source in *Sender Interchange* or *Receiver Interchange*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Business Transaction Activity
    
    </td>
    <td valign="top">
    
    Select the direction of the business transaction activity from the drop-down list.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.

    > ### Note:  
    > You can view these custom search attributes in B2B Monitor tab once the agreement is activated. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)




You have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Activating a Trading Partner Agreement](activating-a-trading-partner-agreement-baed0e3.md "Activate your trading partner agreement to push the agreement details into the SAP Cloud Integration partner directory.")

