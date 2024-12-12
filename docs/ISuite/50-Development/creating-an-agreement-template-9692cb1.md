<!-- loio9692cb19768145c7b265c14612a3e046 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating an Agreement Template

An agreement template is a template of a semantical choreography definition consisting of one or more business transactions. The configurations at the template level serve as defaults that can then be reused and overridden when creating the trading partner agreement.



<a name="loio9692cb19768145c7b265c14612a3e046__prereq_rhv_pwd_lzb"/>

## Prerequisites

The Agreement Template has a new format. The outdated templates are read-only and must be migrated to this new format to enable editing. The following procedure is for the latest template format. To migrate your outdated templates, see [Migrating an Agreement Template](migrating-an-agreement-template-70c469b.md).



## Context

Follow the next procedure to create an agreement template.



## Procedure

1.  Log on to your application.

2.  Choose *Design* \> *B2B Scenarios*.

3.  Navigate to the *Agreement Templates* tab and choose *Create*.

4.  In the *Create Agreement Template* dialog, enable *Create with Company Subsidiary* toggle button if you want to create the template using the subsidiary.

    1.  If selected, the field *Company Subsidiary* gets enabled. Select a subsidiary from the drop-down list..


5.  In the same dialog, enable *Include Communication Partner* toggle button if you want to include a communication partner in the agreement template.

    1.  If the *Include Communication Partner* is selected, the field *Communication Partners* gets enabled. Select a communication partner from the drop-down list.


6.  Choose *Create*.

7.  In the *Overview* tab, enter the following details under the *Details* section:


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
    
    Name of the agreement template
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**
    
    </td>
    <td valign="top">
    
    Provide a description of your agreement template
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Version**
    
    </td>
    <td valign="top">
    
    It is set to *1.0* by default. You can modify this value according to your requirement.
    
    </td>
    </tr>
    </table>
    
8.  Maintain the following fields under *My Company Details* section. The field *Company Name* is autofilled by default.

    > ### Note:  
    > If you selected a Subsidiary during the Template creation step \(refer Step 4\), the *Company Name* field will display the respective Subsidiary's name. Otherwise, it will default to the Company Profile name.


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
    
    **System**
    
    </td>
    <td valign="top">
    
    Select a system from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System**
    
    </td>
    <td valign="top">
    
    Select a type system from the drop-down list.
    
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
    > You need to have the *Business Expert* to assign a contact person. To know more on assigning roles, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System Version**
    
    </td>
    <td valign="top">
    
    Select a type system version from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Identifier in Company Type System**
    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identifier in Trading Partner Type System
    
    </td>
    <td valign="top">
    
    Select the identifier for the trading partner type system. This field should be maintained after entering the *Type System* details for the trading partner in the next step.
    
    </td>
    </tr>
    </table>
    
9.  Under *Common Details* fill in the following details:

    > ### Note:  
    > If you had opted for a communication partner during template creation \(refer Step 5\), then the *Name* field will be populated with the communication partner name.


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
    
    **System \(displayed if you chose a communication partner during template creation\)**
    
    </td>
    <td valign="top">
    
    Select a system for the communication partner.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **System Alias**
    
    </td>
    <td valign="top">
    
    Enter an alias for the trading partner.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System**
    
    </td>
    <td valign="top">
    
    Select a type system for the partner.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System Version**
    
    </td>
    <td valign="top">
    
    Select the version of the type system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Alias for Contact Person**
    
    </td>
    <td valign="top">
    
    Enter an alias for the contact person of the trading partner. This field appears only for *GS1 XML* type system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias for Identifier in Trading Partners Type System
    
    </td>
    <td valign="top">
    
    Enter an alias identifier that will be used for the trading partner in the type system of Trading Partner.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias for Identifier in Company Type System
    
    </td>
    <td valign="top">
    
    Enter an alias identifier that will be used for the trading partner in the type system of Company.
    
    </td>
    </tr>
    </table>
    
10. Choose *Save*. Once you save the agreement template, the template also displays the *Purpose* of the type system you chose.

11. Navigate to the *B2B Scenarios* tab and choose *Create Business Transaction*.

12. In the *Create Business Transaction* dialog, maintain the following details:


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
    
    Select a pattern for the business transaction.
    
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
    
13. Choose *Save*. A new entry gets created.

14. In the newly created transaction, choose the *Communication* step on the sender side.

15. Select a value from the drop-down list for the field *Communication*.

16. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    This field appears only for AS2 adapter.

17. Select the *Interchange* step on the sender side.

18. Set the target decimal value of the incoming payload in the *Target Decimal Character* field.

    This field appears only for the **UN/EDIFACT** type system.

19. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field.

20. In the *Select MIG* dialog, the list of MIGs available in the system is displayed in a table. Use the fields provided \(MIG Name, Version, Status etc.\) to search for a specific MIG.

21. Select a MIG from the list along with the required version and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field. You can also directly view the message type used in the MIG displayed under the *Message Type* field.

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

22. For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.

23. Select a value from the drop-down list for the field *Create Functional Acknowledgement*.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md)

24. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.

25. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

26. If you want to enable the payload validation, select the checkbox *Enable Payload Validation*under *Validation Option* section.

    1.  If enabled, the generic integration flow will perform a validation check for the sender interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


27. The *Syntax Validation* checkbox is selected by default to enable syntax validation through the EDI splitter. If you do not want to use this validation, you can disable this option.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

    If the identifier used in the agreement has **Custom Scheme Code**, then this option will be skipped irrespective of the field selection.

28. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md)

29. Similarly, choose the *Communication Channel* on the receiver side and enter a value for the field *Communication*.

30. Select a value from the drop-down list for the field *Receiver Functional Acknowledgement Channel*.

    This field appears only for AS2 adapter.

31. Select the *Interchange* shape on the receiver side.

32. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

33. Enter an alias value for the field *Number Range Alias*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

34. Similar to the Sender, if you want to use custom integration flows for your Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

35. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

36. Select the *Enable Receiver Functional Acknowledgement* checkbox if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md)

37. If you want to use custom seperators for your payload, enable the *Use Custom Seperators* checkbox and maintain the values for the following fields:

    This option is available only for UN/EDIFACT and ASC X12 type systems.

    1.  Segment Terminator

    2.  Composite Sperator

    3.  Data Element Seperator

    4.  Escape Character


38. If you want to enable the payload validation, select the checkbox for the field *Enable Payload Validation* under *Validation Option*.

    1.  If enabled, the generic integration flow will perform a validation check for the receiver interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


39. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

40. If your receiver type system is UN/EDIFACT, you might want to set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.

41. Select the *Mapping* step of the transaction.

42. Select a mapping guideline and its corresponding version using the value help for the *Mapping Guideline\(MAG\)* field.

43. If you want to custom integration flow for the mapping processing, enable the checkbox for the field *Customized Mapping Processing*.

44. Provide the address of your integration flow in the *Process Direct Address* field.

45. Choose anywhere outside the transaction and the common properties get displayed below the transaction. Choose the *Activity Parameters* tab if you want to add any paramaters to the template.

46. Choose *Add Parameters*. This will display the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile and a Subsidiary](creating-a-company-profile-and-a-subsidiary-909d928.md)

    -   *Create Trading Partner Parameters*: This option allows you to create dynamic parameters for the trading partner profile used in the agreement template.If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. A dialog box with the *Parameter Key* field is displayed. Enter a value for the field and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your onw activity paramaters using this option. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.

47. Navigate to the *Custom Search Attirbutes* tab if you want to add any custom search values which are picked up for the B2B monitoring.

    Before adding custom search attributes, you need to maintain them in the *Configuration Manager*. To know more, see [Configuration Manager](configuration-manager-7daf06c.md).

48. Choose *Add* and maintain the following fields:


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
    
    **Source Value**
    
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
    
    **Business Transaction Activity**
    
    </td>
    <td valign="top">
    
    Select the direction of the business transaction activity from the drop-down list.
    
    </td>
    </tr>
    </table>
    
49. Choose *Save*.




<a name="loio9692cb19768145c7b265c14612a3e046__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Trading Partner Agreement](trading-partner-agreement-9bd43c9.md "Explore and create trading partner agreements.")

