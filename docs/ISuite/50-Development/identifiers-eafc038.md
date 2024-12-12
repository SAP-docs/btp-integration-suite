<!-- loioeafc03833e0b4445a6a179b9af9dc69e -->

# Identifiers

Create and maintain your identifiers.



## Context

Identifiers are unique values that help identify entities in a business transaction. They follow definitions defined by the EDI standards/type systems. There are multiple agencies and schemes under these type systems that are used to define their identifiers, and when maintaing a type system in the agreement, you need to also mention the corresponding identifer. To do so, you need to create identifiers in your company profile/subsidiary.

The *Identifiers* ta consists of two types of identifiers:

-   **Single Identifiers**: These are individual identifiers that have their own type system, scheme and organization etc.

-   **Group Identifiers**: These are group of identifiers that share a common Alias, Type System, Agency and Scheme.



## Procedure

1.  Navigate to the *Identifiers* tab. The tab consists of two sections:

    -   *Single Identifiers*: If you want to create a single identifier, choose *Create* provided above the *Single Identifiers* table and proceed from Step 2 below.

    -   *Identifier Groups*: If you want to create an identifier group, choose *Create* provided above the *Identifier Groups* table and follow the instructions from Step 4 below.

2.  For **Single Identifier**, enter the following details:

    **Identifier**


    <table>
    <tr>
    <th valign="top">

    Field Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Identification
    
    </td>
    <td valign="top">
    
    Provide a valid ID for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    Enter an alias for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System
    
    </td>
    <td valign="top">
    
    Choose a type system from the drop-down list.

    > ### Note:  
    > -   For *GS1 XML* type system, you must maintain the contact details in the *Contacts* tab.
    > 
    > -   For *Tradacoms* type system for the identifier, the field *Identification* is mandatory. If the sender payload contains both *Identification* and *Name*, the integration flow will consider only *Identification* for the computed Partner Directory ID.
    > 
    >     The system ASSEMBLY will use Company profile's *Short Name* for the *Identification Name*
    > 
    >     Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Agency
    
    </td>
    <td valign="top">
    
    Provide the agency name and code in their respective fields.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Custom Scheme

    > ### Note:  
    > This field appears only if you chose *ASC X12* or *UN/EDIFACT* as the type system in the*Type System* field.


    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to use custom scheme for your identifier.

    > ### Caution:  
    > Using Custom Scheme codes will disable EDI envelop validations at the EDI Splitter step. It is recommended to use Standard Scheme codes if you want to retain the validation.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme
    
    </td>
    <td valign="top">
    
    Select a scheme from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme Code

    > ### Note:  
    > This field appears if you have checked the checkbox for *Custom Scheme*. Custom scheme is supported only for ASC X12 and UN/EDIFACT type systems.


    
    </td>
    <td valign="top">
    
    Enter a scheme code.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme Name

    > ### Note:  
    > This field appears if you have checked the checkbox for *Custom Scheme*. Custom scheme is supported only for ASC X12 and UN/EDIFACT type systems.


    
    </td>
    <td valign="top">
    
    Enter your custom scheme name.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.

4.  For **Identifier Group**, maintain the following details:

    **Create Identifier Group**


    <table>
    <tr>
    <th valign="top">

    Field Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Identification
    
    </td>
    <td valign="top">
    
    Provide a valid ID for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    Enter an alias for the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type System
    
    </td>
    <td valign="top">
    
    Choose a type system from the drop-down list.

    > ### Note:  
    > -   For *GS1 XML* type system, you must maintain the contact details in the *Contacts* tab.
    > 
    > -   For *Tradacoms* type system for the identifier, the field *Identification* is mandatory. If the sender payload contains both *Identification* and *Name*, the integration flow will consider only *Identification* for the computed Partner Directory ID.
    > 
    >     The system ASSEMBLY will use Company profile's *Short Name* for the *Identification Name*
    > 
    >     Tradacoms is supported only in the 2.0 version of the integration package *Cloud Integration - Trading Partner Management V2*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Agency
    
    </td>
    <td valign="top">
    
    Provide the agency name and code in their respective fields.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Custom Scheme

    > ### Note:  
    > This field appears only if you chose *ASC X12* or *UN/EDIFACT* as the type system in the*Type System* field.


    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to use custom scheme for your identifier.

    > ### Caution:  
    > Using Custom Scheme codes will disable EDI envelop validations at the EDI Splitter step. It is recommended to use Standard Scheme codes if you want to retain the validation.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme
    
    </td>
    <td valign="top">
    
    Select a scheme from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme Code

    > ### Note:  
    > This field appears if you have checked the checkbox for *Custom Scheme*. Custom scheme is supported only for ASC X12 and UN/EDIFACT type systems.


    
    </td>
    <td valign="top">
    
    Enter a scheme code.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scheme Name

    > ### Note:  
    > This field appears if you have checked the checkbox for *Custom Scheme*. Custom scheme is supported only for ASC X12 and UN/EDIFACT type systems.


    
    </td>
    <td valign="top">
    
    Enter your custom scheme name.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*. The identifier group is created successfully. You need to now add identifiers to it.

6.  Open the identifier group from the *Identifier Groups* table.

7.  Choose *Edit* to edit the details of the group.

8.  Select *Add* above the *Identifiers in Group* to add idenifiers to this group.

9.  Maintain the values for *Identification* and *Sub-Organization* fields and choose *Save*.

10. Choose *Activate* to activate the group and publish its identifier details into the partner directory. This step just publishes the content and the identifiers would take effect only if any agreement using the identifier group gets activated.

11. If you make any changes after the activation of the group and want to push the latest changes to the Partner Directory, save your changes and choose *Update*.

12. Navigate to the *Business Context* tab, and follow the procedure mentioned here: [Business Context](business-context-f064431.md).


