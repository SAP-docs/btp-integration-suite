<!-- loioa6ee60308011402abd8fe9ac1bc5a460 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modifying SuccessFactors SOAP Entity and Operation



## Prerequisites

-   You're configuring the communication channel that is assigned with the SuccessFactors SOAP adapter.

-   The TrustedCAs from the service provider you're connecting to have been added to the system keystore associated with your HCI account.




## Context

The SuccessFactors SOAP adapter enables you to modify the entity that you're accessing and the operation that you're performing on the entity. You can use this adapter to perform the following operations:

-   Query

-   Insert

-   Update

-   Upsert


You use the following procedure to change the entity and modify the operation for the SuccessFactors SOAP adapter.



<a name="loioa6ee60308011402abd8fe9ac1bc5a460__steps_h31_qsp_gr"/>

## Procedure

1.  If you'ven't added a system with authentication details, choose :heavy_plus_sign: and provide values in the fields, based on the descriptions in the following table. Choose *Connect*.


    <table>
    <tr>
    <th valign="top">

    Fields
    
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
    
    Name of the SuccessFactors data center that you're connecting to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select one of the following authentication methods:

    -   *Basic*

    -   *OAuth2 SAML Bearer Assertion* – in the query modeler, principal propagation isn't supported. Use a technical user ID with key pair common name. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](deploying-an-oauth2-saml-bearer-assertion-3ee6582.md).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    URL of the SuccessFactors data center that you're connecting to
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address Suffix
    
    </td>
    <td valign="top">
    
    The field is auto-populated with `/sfapi/v1/soap`. Don't edit the field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name
    
    </td>
    <td valign="top">
    
    Name of the credentials that you've deployed in *Security Material* section in Operations View.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Company ID

    Only if you choose Basic authentication and don't want to use a deployed credential.
    
    </td>
    <td valign="top">
    
    Company ID for authentication
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Name

    Only if you choose Basic authentication and don't want to use a deployed credential.
    
    </td>
    <td valign="top">
    
    User name associated with the company ID
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password

    Only if you choose Basic authentication and don't want to use a deployed credential.
    
    </td>
    <td valign="top">
    
    Relevant password for the specified user name
    
    </td>
    </tr>
    </table>
    
2.  If you've added a system with authentication details, perform the following substeps:

    1.  In the *System* field, choose the system you want to connect to from the dropdown list.

    2.  For authentication, choose between *Basic* or *OAuth2 SAML Bearer Assertion*.

    3.  If you choose Basic authentication and don't want to use a deployed credential, provide the user name and password in the appropriate fields.

    4.  If you choose Basic authentication with credential name or OAuth2, provide the name of the credentials that you've deployed in *Security Material* section in Operations View.

    5.  Choose *Connect*.


3.  In the *Entity Selection* dialog, select the entity that you want to access.

4.  In *Operation* dropdown list, choose the operation that you want to perform.

    > ### Note:  
    > You can only perform the Query operation in the sender channel.

5.  In the *Fields* dropdown list, select the fields that you want to perform the operation on.

    > ### Note:  
    > You can select multiple fields by selecting their respective checkboxes. Choose the operation you want to perform.

6.  If you want to specify filter conditions, choose the <span class="SAP-icons-V5"></span> icon, select the operation you want to use, and perform the following substeps:

    1.  In the *Filter By* field, enter the fields that you want to filter.

    2.  In the *Operator* dropdown list, select the operator that you want to use to define the filter condition.

    3.  In the *Input Type* field, select the type of input you want to provide for defining the filter condition.

    4.  In the *Value* field, provide the value of the input for the filter condition.

    5.  Select *AND* or *OR* based on how you want this filter condition to be evaluated when the operation is executed.

    6.  Choose :gear: ** \> *Add* to add more than one filter condition.


7.  If you want to specify sorting conditions, choose <span class="SAP-icons-V5"></span> and perform the following substeps:

    1.  In the *Field* field, enter the field on which you want to do the sorting.

    2.  If you want the sorting to be done in descending order, select the checkbox in the *Desc* column.

    3.  Choose :gear: and then :heavy_plus_sign: to add more sorting condition.





## Results

The system displays a message that an XSD file has been created. You can use this XSD file for mapping steps.

