<!-- loio934bbcd671334533a60bdaf073961be7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding Custom Search Attributes

Add Custom Search Attributes to your agreement.



<a name="loio934bbcd671334533a60bdaf073961be7__prereq_hw3_f2s_zcc"/>

## Prerequisites

You have defined custom search attributes in the *Configuration Manager* tab. See [Configuration Manager](configuration-manager-7daf06c.md).



## Context

Custom search attributes allow you to search for interchanges based on the user-defined filters in the **Monitor** section. To add custom search attributes to the transaction, perform the steps below:



## Procedure

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
    > You can view these custom search attributes in B2B Monitor tab once the agreement is activated. To know more, see [Update Agreements](update-agreements-b5e1fc9.md).




<a name="loio934bbcd671334533a60bdaf073961be7__result_ugr_vpb_3cc"/>

## Results

With this, you have now successfully created a trading partner agreement and you can view the agreement details under the *Agreements* tab. You can also view the administrative information under the tab. To enable those fields, choose *Settings* :gear: icon and select the following fields and choose *OK*:

-   Created By

-   Created Date
-   Last Modified By
-   Modified Date

