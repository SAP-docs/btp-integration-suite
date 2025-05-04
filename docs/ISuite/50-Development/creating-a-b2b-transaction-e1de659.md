<!-- loioe1de65974df9484091e0adeb7719c4dc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a B2B Transaction

Navigate to the B2B Scenarios tab and choose Create Business Transaction. Use it to initiate B2B transactions efficiently and accurately.



## Context



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
    
    Select this checkbox if the transaction is a pass-through entity, requiring no additional configuration or processing beyond forwarding the data. The following procedure is for a standard B2B transaction. If you have enabled this checkbox, you need to configure the transaction based on the steps mentioned in [Creating a Pass-Through B2B Transaction](creating-a-pass-through-b2b-transaction-6dd03a4.md)
    
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

6.  Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    This field appears only for AS2 adapter.

7.  Select the *Interchange* step on the sender side.

8.  Set the target decimal value of the incoming payload in the *Target Decimal Character* field.

    This field appears only for the **UN/EDIFACT** type system.

9.  Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field.

10. In the *Select MIG* dialog, the list of MIGs available in the system is displayed in a table. Use the fields provided \(MIG Name, Version, Status etc.\) to search for a specific MIG.

11. Select a MIG from the list along with the required version and select *Choose*.

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

12. For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.

13. Select a value from the drop-down list for the field *Create Functional Acknowledgement*.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12


    To configure the **interchange number**, maintain the following properties:


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
    
    *Interchange Number*

    \(only configurable if you select *Create Functional Acknowledgement*, either with the option *Check EDI Envelop* or *Required*\)
    
    </td>
    <td valign="top">
    
    Trading Partner Management adds the interchange number in the functional acknowledgement of an EDI message. Select one of the following options:

    -   *Use from EDI Message*: Reads the interchange number from the EDI message

    -   *Number Range*: Reads the interchange number from an assigned set of number ranges



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Unique Interchange Number*

    \(only configurable if you selected *Number Range* as the value for field *Interchange Number*\)
    
    </td>
    <td valign="top">
    
    Select your desired behavior for generating a unique interchange number while generating an acknowledgement message:

    -   *Required*: The EDI Splitter can generate a unique interchange number, which is the incremented value from the number range object and doesn't depend on the interchange number of the incoming payload.

    -   *Not Required*: Doesn't generate a unique interchange number.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Number Range*

    \(only configurable if you selected *Number Range* as the value for field *Interchange Number*\)
    
    </td>
    <td valign="top">
    
    Select the number range assigned to an interchange number in the functional acknowledgement. Number ranges are defined in the corresponding profile.

    If *Unique Interchange Number* is set as *Required*, a new interchange number is generated for every incoming message.

    If *Unique Interchange Number* is set as *Not Required*, a new interchange number is generated only for unique incoming messages. Duplicate incoming messages are assigned the same interchange number for 30 days.
    
    </td>
    </tr>
    </table>
    
    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To learn more, see [Update Agreements](update-agreements-b5e1fc9.md).

14. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.

15. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

16. If you want to enable the payload validation, select the checkbox *Enable Payload Validation* under *Validation Option* section.

    1.  If enabled, the generic integration flow will perform a validation check for the sender interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


17. The *Syntax Validation* checkbox is selected by default to enable syntax validation through the EDI splitter. If you do not want to use this validation, you can disable this option.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

    If the identifier used in the agreement has **Custom Scheme Code**, then this option will be skipped irrespective of the field selection.

18. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

19. Similarly, choose the *Communication Channel* on the receiver side and enter a value for the field *Communication*.

20. Select a value from the drop-down list for the field *Receiver Functional Acknowledgement Channel*.

    This field appears only for AS2 adapter.

21. Select the *Interchange* shape on the receiver side.

22. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

23. Enter an alias value for the field *Number Range Alias*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

24. Similar to the Sender, if you want to use custom integration flows for your Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

25. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

26. Select the *Enable Receiver Functional Acknowledgement* checkbox if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Update Agreements](update-agreements-b5e1fc9.md)

27. If you want to use custom separators for your payload, enable the *Use Custom Separators* checkbox and maintain the values for the following fields:

    This option is available only for UN/EDIFACT and ASC X12 type systems.

    1.  Segment Terminator

    2.  Composite Separator

    3.  Data Element Separator

    4.  Escape Character


28. If you want to enable the payload validation, select the checkbox for the field *Enable Payload Validation* under *Validation Option*.

    1.  If enabled, the generic integration flow will perform a validation check for the receiver interchange. And regardless of the outcome, the interchange processing will continue to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


29. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

30. If your receiver type system is UN/EDIFACT, you might want to set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.

31. Select the *Mapping* step of the transaction.

32. Select a mapping guideline and its corresponding version using the value help for the *Mapping Guideline \(MAG\)* field.

33. If you want to custom integration flow for the mapping processing, enable the checkbox for the field *Customized Mapping Processing*.

34. Provide the address of your integration flow in the *Process Direct Address* field.

35. Choose anywhere outside the transaction and the common properties get displayed below the transaction. Choose the *Activity Parameters* tab if you want to add any parameters to the template.

36. Choose *Add Parameters*. This will display the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile and a Subsidiary](creating-a-company-profile-and-a-subsidiary-909d928.md)

    -   *Create Trading Partner Parameters*: This option allows you to create dynamic parameters for the trading partner profile used in the agreement template. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. A dialog box with the *Parameter Key* field is displayed. Enter a value for the field and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your own activity parameters using this option. If you have created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.

37. Navigate to the *Custom Search Attributes* tab if you want to add any custom search values which are picked up for the B2B monitoring.

    Before adding custom search attributes, you need to maintain them in the *Configuration Manager*. To know more, see [Configuration Manager](configuration-manager-7daf06c.md).

38. Choose *Add* and maintain the following fields:


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
    
39. Choose *Save*.




<a name="loioe1de65974df9484091e0adeb7719c4dc__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

