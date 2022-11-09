<!-- loio9bd43c9ae064493286f321551bd0557c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Trading Partner Agreement

A trading partner agreement is an agreement of a contract defined by two trading parties that have decided to exchange certain business data or items using a B2B scenario for fullfilling the agreed trading/business process in a given business context.

Creating an agreement is the last step in the design of a B2B transaction and consists of tow trading partners representing one type of transaction between those two partners. Follow the procedure below to create a trading partner agreement.

1.  Login to your application and navigate to *Agreements* tab.

2.  Choose *Create*. This will display a list of agreement templates available in the system. Select an agreement from the list and choose *OK*.

    > ### Note:  
    > SAP does not provide any pre-defined templates. Ensure you have the required template created before creating an agreement.

3.  In the *Overview* tab, maintain the following fields under the *Details* section

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
    
4.  Maintain the following fields under *My Company Details* section

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
    
5.  Maintain the following fields under *Trading Partner Details* section

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
    
6.  Choose *Save*.
7.  Navigate to the *B2B Scenarios* tab. This tab displays the transactions that are created under the agreement template.
8.  Choose the *Communication Channel* step on the sender side.
9.  Select a value from the drop-down list for the field *Communication*.
10. Select a value from the drop-down list for the field *Communication for Sender Functional Acknowledgement*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

11. Select the *Interchange* step on the sender side.
12. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

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

13. Select a value from the drop-down list for the field *Create Acknowledgement*.

    > ### Note:  
    > This field appears only for the following type systems:
    > 
    > -   UN/EDIFACT
    > 
    > -   ASC X12
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

14. If you are planning to use custom integration flows for Pre-Processing and Post-Processing of your interchange step, then enable the checkbox under *Custom Integration Flow*.
15. Provide the name of your custom integration flow in the *Integration Flow Name* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](https://help.sap.com/viewer/9e51bec2356e4664b6d5fd1a336a9e12/Cloud/en-US/7d3bce9478974229af1abf9121fe47e6.html "This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.") :arrow_upper_right:

16. Choose the *Mapping* step on the sender side.
17. Select a mapping guideline using the value help provided for the field *Mapping Guideline\(MAG\)*.

    If you want to view the details of the MAG that you chose, you can use the link provided under the *Version* field.

18. Choose the *Communication Channel* on the receiver side and select a value from the drop-down list for the field *Communication*.
19. Select the value for the field *Receiver Functional Acknowledgement Channel*.

    > ### Note:  
    > This field appears only for AS2 adapter.
    > 
    > You can view the status of the Functional Acknowledgement through the *Monitor* tab. To know more, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

20. Select the *Interchange* shape on the receiver side.
21. Choose the value help provided for the *Message Implementation Guideline \(MIG\)* field and select a MIG from the list and select *Choose*.

    > ### Note:  
    > If you want to view the details of the MIG that you chose, you can use the link provided under the *Version* field.

22. Select a value from the drop-down list for the field *Number Range*.

    > ### Note:  
    > A number range is used to insert unique sequence numbers.
    > 
    > You need to configure this number range in the Cloud Integration tenant. To do so, see [Number Ranges](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b6e17fa17a70491da4a54216db298f84.html).

23. Similar to the Sender, if you want to use custom integration flows for your Pre/Post-Processing of the interchange step, enable the checkbox under *Custom Integration Flow*.
24. Provide the name of your custom integration flow in the *Integration Flow Name* field.

    > ### Note:  
    > To know more about how it works, see [Interchange Processing Flow](https://help.sap.com/viewer/9e51bec2356e4664b6d5fd1a336a9e12/Cloud/en-US/7d3bce9478974229af1abf9121fe47e6.html "This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.") :arrow_upper_right:

25. Select the *Enable* checkbox under *Receiver Functional Acknowledgement* if you want to enable the functional acknowledgement for the receiver.

    > ### Note:  
    > This option is available only for the following type systems:
    > 
    > -   UN/EDIFACT
    > -   ASC X12

26. Choose *Save*.

You have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Activating a Trading Partner Agreement](activating-a-trading-partner-agreement-baed0e3.md "Activate your trading partner agreement to push the agreement details into the SAP Cloud Integration partner directory.")

