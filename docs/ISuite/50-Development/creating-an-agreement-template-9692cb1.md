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

4.  In the *Create Agreement Template* dialog, enable the *Include Communication Partner* toggle button if you want to include a communication partner in the agreement templet.

5.  If the *Include Communication Partner* is selected, the field *Communication Partners* gets enabled. Select a communication partner from the drop-down list and choose *Create*.

6.  In the *Overview* tab, enter the following details under the *Details* section:


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
    
7.  Maintain the following fields under *My Company Details* section. The field *Company Name* is autofilled by default.


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
    
8.  Under *Common Details* fill in the following details:


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
    
    **System Alias**
    
    </td>
    <td valign="top">
    
    Maintain an alias value for the system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System**
    
    </td>
    <td valign="top">
    
    Select a type system for the trading partner.
    
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
    
9.  Choose *Save*. Once you save the agreement template, the template also displays the *Purpose* of the type system you chose.

10. Navigate to the *B2B Scenarios* tab and choose *Create Business Transaction*.

11. In the *Create Business Transaction* dialog, maintain the following details:


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
    
12. Choose *Save*. A new entry gets created.

13. In the newly created transaction, choose the *Communication Channel* step on the sender side.

14. Select a value from the drop-down list for the field *Communication*.

15. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    This field appears only for AS2 adapter.

16. Select the *Interchange* step on the sender side.

17. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field.

18. Select a MIG from the list along with the required version and select *Choose*.

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

19. For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.

20. Select a value from the drop-down list for the field *Create Functional Acknowledgement*.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

21. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.

22. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

23. If you want to enable the payload validation, select the checkbox under *Validation Option*.

24. The *Syntax Validation* checkbox is selected by default to enable syntax validation through the EDI splitter. If you do not want to use this validation, you can disable this option.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

25. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:5" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9692cb19768145c7b265c14612a3e046.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

26. Similarly, choose the *Communication Channel* on the receiver side and enter a value for the field *Alias for Communication*.

27. Select a value from the drop-down list for the field *Receiver Functional Acknowledgement Channel*.

    This field appears only for AS2 adapter.

28. Select the *Interchange* shape on the receiver side.

29. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

30. Enter an alias value for the field *Number Range Alias*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

31. Similar to the Sender, if you want to use custom integration flows for your Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

32. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

33. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

34. If you want to enable the payload validation, select the checkbox under *Validation Option*.

35. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see  <?sap-ot O2O class="- topic/xref " href="b927e0182df04208ace0f15c66073317.xml" text="" desc="" xtrc="xref:9" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/9692cb19768145c7b265c14612a3e046.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

36. If your receiver type system is UN/EDIFACT, you might want to set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.

37. Select the *Mapping* step of the transaction.

38. Select a mapping guideline and its corresponding version using the value help for the *Mapping Guideline\(MAG\)* field.

39. If you want to custom integration flow for the mapping processing, enable the checkbox for the field *Customized Mapping Processing*.

40. Provide the address of your integration flow in the *Process Direct Address* field.

41. Choose anywhere outside the transaction and the common properties get displayed below the transaction. Choose the *Activity Parameters* tab if you want to add any paramaters to the template.

42. Choose *Add Parameters*. This will display the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile](creating-a-company-profile-909d928.md)

    -   *Create Trading Partner Parameters*: This option allows you to create dynamic parameters for the trading partner profile used in the agreement template.If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. A dialog box with the *Parameter Key* field is displayed. Enter a value for the field and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your onw activity paramaters using this option. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.

43. Navigate to the *Custom Search Attirbutes* tab if you want to add any custom search values which are picked up for the B2B monitoring.

    Before adding custom search attributes, you need to maintain them in the *Configuration Manager*. To know more, see [Configuration Manager](configuration-manager-7daf06c.md).

44. Choose *Add* and maintain the following fields:


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
    
45. Choose *Save*.




<a name="loio9692cb19768145c7b265c14612a3e046__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Creating a Trading Partner Agreement](creating-a-trading-partner-agreement-9bd43c9.md "A trading partner agreement is an agreement of a contract defined by two trading parties that have decided to exchange certain business data or items using a B2B scenario for fullfilling the agreed trading/business process in a given business context.")

