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

11. Now you need to create a B2B transaction. To do so, follow the procedure mentioned in [Creating a B2B Transaction](creating-a-b2b-transaction-e1de659.md).

    If you want to create a pass-through transaction, see [.](creating-a-pass-through-b2b-transaction-6dd03a4.md)




<a name="loio9692cb19768145c7b265c14612a3e046__result_ckl_5j5_pqb"/>

## Results

You have now successfully created an agreement template and you can view the template details under the *Agreement Templates* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

**Related Information**  


[Trading Partner Agreement](trading-partner-agreement-9bd43c9.md "Explore and create trading partner agreements.")

