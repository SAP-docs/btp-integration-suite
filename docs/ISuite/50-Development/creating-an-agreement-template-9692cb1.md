<!-- loio9692cb19768145c7b265c14612a3e046 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating an Agreement Template

An agreement template is a template of a semantical choreography definition consisting of one or more business transactions. The configurations at the template level serve as defaults that can then be reused and overridden when creating the trading partner agreement.



## Context

Follow the procedure below to create an agreement template.

> ### Note:  
> You can only fill in the company details in an agreement template. The trading partner details are required once the agreement is created from the template.



## Procedure

1.  Log on to your Integration Suite .

2.  Choose *Design* \> *B2B Scenarios*.

3.  Navigate to the *Agreement Templates* tab and choose *Create*.

4.  In the *Overview* tab, enter the following details under the *Details* section:


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
    
5.  Maintain the following fields under *My Company Details* section


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
    
    Select a system from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System**


    
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
    > You need to have the *Business Expert* to assign a contact person. To know more on assigning roles, see [Configuring User Access](../configuring-user-access-2c6214a.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System Version**


    
    </td>
    <td valign="top">
    
    Select a type system version from the drop-down list


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Identifier**


    
    </td>
    <td valign="top">
    
    Select an identifier using the value help provided


    
    </td>
    </tr>
    </table>
    
6.  Choose *Save*. Once you save the agreement template, the template also displays the *Purpose* of the type system you chose.

7.  Navigate to the *B2B Scenarios* tab and choose *Edit*.

8.  Choose *Create Business Transaction*.

9.  Maintain the following details :


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
    
    Provide a name for your business transaction


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Business Transaction Pattern**


    
    </td>
    <td valign="top">
    
    Select a pattern for the business transaction


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **My Company Role**


    
    </td>
    <td valign="top">
    
    Check the radio button based on whether your company is an *Initiator* or *Reactor*


    
    </td>
    </tr>
    </table>
    
10. Choose *Save*. A new entry gets created.

11. In the newly created transaction, choose the *Communication Channel* step on the sender side.

12. Select a value from the drop-down list for the field *Communication*.

13. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    This field appears only for AS2 adapter.

14. Select the *Interchange* step on the sender side.

15. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field.

16. Select a MIG from the list along with the required version and select *Choose*.

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

17. For Type Systems *ASC X12* and *UN/EDIFACT*, you can edit their version numbers in the *Type System Version* field.

18. Select a value from the drop-down list for the field *Create Functional Acknowledgement*.

    This field appears only for the following type systems:

    -   UN/EDIFACT

    -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

19. If you are planning to use custom integration flows for Pre-Processing and Post-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.

20. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

21. Similarly, choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.

22. Select a value from the drop-down list for the field *Receiver Functional Acknowledgement Channel*.

    This field appears only for AS2 adapter.

23. Select the *Interchange* shape on the receiver side.

24. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

25. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

26. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.

27. Provide the address of your custom integration flow in the *Process Direct Address* field.

    This step is carried out using the ProcessDirect adapter. To know more about how it works, see [Interchange Processing Flow](interchange-processing-flow-7d3bce9.md)

28. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

    You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

29. Choose *Parameters* if you want to add any paramaters to the template.

30. In the *Parameters* tab displayed, choose *Add Parameters*. This will display the following options:

    -   *Extend from Company*: This option allows you to use the dynamic parameters from the company profile used in the agreement template. You can choose either *Request* or *Response* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a company profile, see [Creating a Company Profile](creating-a-company-profile-909d928.md)

    -   *Extend from TP*: This option allows you to use the dynamic parameters from the trading partner profile used in the agreement template. You can choose either *Request* or *Response* and this will display the list of parameters respectively. Select a parameter from the list and choose *Save*.

        If you want to know how to add dynamic parameters to a trading partner profile, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md) 

    -   *Create Activity Parameters*: You can also create your onw activity paramaters using this option. Select this option and choose *Request* or *Response*. Maintain the values of the fields *Parameter Key* and *Value* and choose *Create*.

31. Choose *Save*.




<a name="loio9692cb19768145c7b265c14612a3e046__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Creating a Trading Partner Agreement](creating-a-trading-partner-agreement-9bd43c9.md "A trading partner agreement is an agreement of a contract defined by two trading parties that have decided to exchange certain business data or items using a B2B scenario for fullfilling the agreed trading/business process in a given business context.")

