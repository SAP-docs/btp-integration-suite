<!-- loioe1de65974df9484091e0adeb7719c4dc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a B2B Transaction

Under *B2B Scenarios* \> *Create Business Transaction*, you can initiate B2B transactions efficiently and accurately.



## Procedure

1.  In your agreement template, navigate to the *B2B Scenarios* tab and choose *Create Business Transaction*.

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
    
    Select this checkbox if the transaction is a pass-through entity, requiring no additional configuration or processing beyond forwarding the data. The following procedure is for a standard B2B transaction. If you've enabled this checkbox, you need to configure the transaction based on the steps mentioned in [Creating a Pass-Through B2B Transaction](creating-a-pass-through-b2b-transaction-6dd03a4.md).
    
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
    
3.  Choose *Save*. A new entry is created.

    > ### Note:  
    > If you're working with multiple business transactions, you can reorder them for an aligned visual representation: Choose *Change Order*, then use *Move Up* and *Move Down* to rearrange the transactions. The new order is applied as soon as you save.
    > 
    > Reordering the transactions has no effect on functionality or outcomes and is for visual alignment only.

4.  In the newly created transaction, choose the *Communication* step on the sender side.

5.  Select a value from the drop-down list for the field *Communication*.

6.  Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    This field appears only for the AS2 adapter.

7.  Select the *Interchange* step on the sender side.

8.  Set the target decimal value of the incoming payload in the *Target Decimal Character* field.

    This field appears only for the **UN/EDIFACT** type system.

9.  Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field.

10. In the *Select MIG* dialog, the list of MIGs available in the system is displayed in a table. Use the fields provided \(MIG Name, Version, Status, and so on\) to search for a specific MIG.

11. Select a MIG from the list along with the required version and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field. You can also directly view the message type used in the MIG displayed under the *Message Type* field.

    > ### Note:  
    > -   Ensure you have the required MIG created in the Integration Advisor.
    > 
    > -   Trading Partner Management only supports the following type systems:
    >     -   Edifact
    > 
    >     -   GS1 EANCOM
    >     -   Odette EDIFACT
    >     -   VDA EDIFACT
    >     -   X12
    >     -   SAP IDoc
    >     -   SAP SOAP On-Premise
    >     -   SAP SOAP Cloud
    >     -   GS1 XML
    >     -   Tradacoms
    > 
    >         Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*

12. For Type Systems *ASC X12*, *UN/EDIFACT*, *GS1 EANCOM*, *Odette EDIFACT*, and *VDA EDIFACT*, you can edit their version numbers in the *Type System Version* field.

13. For the type systems *UN/EDIFACT*, *GS1 EANCOM*, *Odette EDIFACT*, *VDA EDIFACT*, and *ASC X12*, you can select a value for *Send Test Interchange to Target System*:

    -   Select *No* if you don't want to send the test payload to the target system.
    -   Select *Yes* if you want to send the test payload to the target system.

    Additionally, the identified usage indicator in monitoring is displayed as either *Production* or *Test*, depending on the following factors:

    -   For type systems *UN/EDIFACT*, *GS1 EANCOM*, *Odette EDIFACT*, and *VDA EDIFACT*, the usage indicator is located at the last position of the UNB segment. `1` signifies a test message, while `2` or the absence of `1` indicates a production message.
    -   For the type system *ASC X12*, ISA15 holds the usage indicator. `T` signifies a test message, whereas `P` or the absence of `T` indicates a production message.

14. Select a value from the drop-down list for the field *Create Functional Acknowledgement*.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   GS1 EANCOM

    -   Odette EDIFACT

    -   VDA EDIFACT

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

    \(only configurable if you selected *Number Range* as the value for the field *Interchange Number*\)
    
    </td>
    <td valign="top">
    
    Select your desired behavior for generating a unique interchange number while generating an acknowledgment message:

    -   *Required*: The EDI Splitter can generate a unique interchange number, which is the incremented value from the number range object and doesn't depend on the interchange number of the incoming payload.

    -   *Not Required*: Doesn't generate a unique interchange number.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Number Range*

    \(only configurable if you selected *Number Range* as the value for the field *Interchange Number*\)
    
    </td>
    <td valign="top">
    
    Select the number range assigned to an interchange number in the functional acknowledgment. Number ranges are defined in the corresponding profile.

    If *Unique Interchange Number* is set as *Required*, a new interchange number is generated for every incoming message.

    If *Unique Interchange Number* is set as *Not Required*, a new interchange number is generated only for unique incoming messages. Duplicate incoming messages are assigned the same interchange number for 30 days.
    
    </td>
    </tr>
    </table>
    
    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To learn more, see [Update Agreements](update-agreements-b5e1fc9.md).

15. If you are planning to use custom integration flows for Pre-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.

16. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

17. If you want to enable the payload validation, select the checkbox *Enable Payload Validation* under *Validation Option* section.

    1.  If enabled, the generic integration flow performs a validation check for the sender interchange. And regardless of the outcome, the interchange processing continues to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


18. The *Syntax Validation* checkbox is selected by default to enable syntax validation through the EDI splitter. If you do not want to use this validation, you can disable this option.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   GS1 EANCOM

    -   Odette EDIFACT

    -   VDA EDIFACT

    -   ASC X12


    If the identifier used in the agreement has **Custom Scheme Code**, then this option is skipped irrespective of the field selection.

19. For sender type systems *UN/EDIFACT*, *GS1 EANCOM*, *Odette EDIFACT*, *VDA EDIFACT*, *ASC X12*, or *TRADACOMS*: use the field *Source Encoding* to let the generic integration flow know the source encoding so it can convert the sender payload to UTF-8 correctly.

    To do so, under the field *Source Encoding*, select a value from the list.

20. To archive the sender payload, select the checkbox for the field *Archive Sender Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

21. Similarly, choose the *Communication Channel* on the receiver side and enter a value for the field *Communication*.

22. Select a value from the drop-down list for the field *Receiver Functional Acknowledgement Channel*.

    This field appears only for the AS2 adapter.

23. Select the *Interchange* shape on the receiver side.

24. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

25. Enter an alias value for the field *Number Range Alias*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

26. Similar to the Sender, if you want to use custom integration flows for your Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

27. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md).

28. Select the *Enable Receiver Functional Acknowledgement* checkbox if you want to enable the functional acknowledgment for the receiver.

    Once it's enabled, use the drop-down list of *Mark Partially Accepted Acknowledgment* to indicate whether the interchange should be marked as *Failed* or *Completed* upon receiving a partially accepted acknowledgment.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   GS1 EANCOM
    > -   Odette EDIFACT
    > -   VDA EDIFACT
    > -   ASC X12

    You can view the status of the functional acknowledgment through the *Monitor* tab. See [Update Agreements](update-agreements-b5e1fc9.md).

29. If you want to use custom separators for your payload, enable the *Use Custom Separators* checkbox and maintain the values for the following fields:

    This option is available only for UN/EDIFACT, GS1 EANCOM, Odette EDIFACT, VDA EDIFACT, and ASC X12 type systems.

    1.  Segment Terminator

    2.  Composite Separator

    3.  Data Element Separator

    4.  Escape Character


30. If you want to enable the payload validation, select the checkbox for the field *Enable Payload Validation* under *Validation Option*.

    1.  If enabled, the generic integration flow performs a validation check for the receiver interchange. And regardless of the outcome, the interchange processing continues to run. If you want to stop processing the interchange when payload validation fails, enable the checkbox for the field *Stop Processing if Payload Validation Fails*.


31. To archive the receiver payload, select the checkbox for the field *Archive Receiver Payload*. To know more about archiving data, see [Archiving Payload Data](archiving-payload-data-b927e01.md).

32. If your receiver type system is UN/EDIFACT, GS1 EANCOM, Odette EDIFACT, VDA EDIFACT, ASC X12, or TRADACOMS, you can set a target encoding. To do so, under the field *Target Encoding*, select a value from the list.

33. Select the *Mapping* step of the transaction.

34. Select a mapping guideline and its corresponding version using the value help for the *Mapping Guideline \(MAG\)* field.

35. If you want to custom integration flow for the mapping processing, enable the checkbox for the field *Customized Mapping Processing*.

36. Provide the address of your integration flow in the *Process Direct Address* field.

37. Choose anywhere outside the transaction and the common properties get displayed below the transaction. Choose the *Activity Parameters* tab if you want to add any parameters to the template.

38. Choose *Add Parameters*. This displays the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. If you've created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile and a Subsidiary](creating-a-company-profile-and-a-subsidiary-909d928.md)

    -   *Create Trading Partner Parameters*: This option allows you to create dynamic parameters for the trading partner profile used in the agreement template. If you've created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. A dialog box with the *Parameter Key* field is displayed. Enter a value for the field and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your own activity parameters using this option. If you've created a *two-way* business transaction, you can choose between *Inbound* or *Outbound* parameters. Maintain the values of the fields *Parameter Key* and *Value* and choose *Save*.

39. Navigate to the *Custom Search Attributes* tab if you want to add any custom search values which are picked up for the B2B monitoring.

    Before adding custom search attributes, you need to maintain them in the *Configuration Manager*. To know more, see [Configuration Manager](configuration-manager-7daf06c.md).

40. Choose *Add* and maintain the following fields:


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
    
    Select a value from the list of attributes that you've created.
    
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
    
41. Choose *Save*.




<a name="loioe1de65974df9484091e0adeb7719c4dc__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose :gear: and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

