<!-- loio8c36fd29df9a4e7bae8ce2699f6abbfd -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Configuring Connectivity to an SAP Process Orchestration System

Learn how to connect an SAP Process Orchestration system.

<a name="task_gb4_43z_wxb"/>

<!-- task\_gb4\_43z\_wxb -->

## Recommended Approach: Using *System* Settings



<a name="task_gb4_43z_wxb__prereq_nvn_jt1_wxb"/>

## Prerequisites

-   You must have tenant administrator role to configure connectivity to an SAP Process Orchestration system.

-   You have completed the tasks mentioned in [Importing Content from SAP Process Orchestration System](importing-content-from-sap-process-orchestration-system-53db5fb.md).




<a name="task_gb4_43z_wxb__steps_m2v_p3z_wxb"/>

## Procedure

1.  Choose *Settings* \> *Integrations*.

2.  Choose the *System* tab.

    If there are SAP Process Orchestration systems already added, you see them. Select an existing system and choose *Edit* to update the configurations.

3.  Choose :heavy_plus_sign: to connect an SAP PO system.

4.  Provide a *System Name* for the PO system that you want to connect to.

    The name that you provide here appears at all places in the tenant when integration developers try to fetch content from a PO system. Make sure that you provide a meaningful name.

5.  Select the *Version* of your PO system.

6.  Optional: Provide a description that explains the PO system.

7.  Enter values in fields based on description in the following table:

    **Integration Directory**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Address*
    
    </td>
    <td valign="top">
    
    Provide the URL from Cloud Connector that connects to your PO system.

    > ### Note:  
    > If the test connection fails, try removing the charcter "`_`" \(underscore\) in the address field in your Cloud Connector. Then, provide the updated URL. An underscore is a likely candidate for such connection failures.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User ID*
    
    </td>
    <td valign="top">
    
    Add the user ID \(technical user\) from your SAP Process Orchestration system.

    > ### Note:  
    > The user must be assigned to the following roles in your SAP Process Orchestration system:
    > 
    > -   `SAP_XI_API_DISPLAY_J2EE`
    > -   `SAP_XI_API_DEVELOP_J2EE`
    > -   `SAP_XI_MONITOR_J2EE`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Add the user's password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Confirm Password*
    
    </td>
    <td valign="top">
    
    Enter the password again.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*
    
    </td>
    <td valign="top">
    
    Add the location ID.
    
    </td>
    </tr>
    </table>
    
8.  **Optional**: If you're using a central Enterprise Services Repository \(ESR\), uncheck the *Same as Integration Directory* check box. Enter values in fields based on description in the following table:

    **ES Repository**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Address*
    
    </td>
    <td valign="top">
    
    Provide the URL from Cloud Connector that connects to your PO system.

    > ### Note:  
    > If the test connection fails, try removing the charcter "`_`" \(underscore\) in the address field in your Cloud Connector. Then, provide the updated URL. An underscore is a likely candidate for such connection failures.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User ID*
    
    </td>
    <td valign="top">
    
    Add the user ID \(technical user\) from your SAP Process Orchestration system.

    > ### Note:  
    > The user must be assigned to the following roles in your SAP Process Orchestration system:
    > 
    > -   `SAP_XI_API_DISPLAY_J2EE`
    > -   `SAP_XI_API_DEVELOP_J2EE`
    > -   `SAP_XI_MONITOR_J2EE`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Add the user's password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Confirm Password*
    
    </td>
    <td valign="top">
    
    Enter the password again.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*
    
    </td>
    <td valign="top">
    
    Add the location ID.
    
    </td>
    </tr>
    </table>
    
9.  Choose *Save*.


<a name="task_jzq_y3z_wxb"/>

<!-- task\_jzq\_y3z\_wxb -->

## Alternative Approach: Creating Destinations in SAP BTP Subaccount



<a name="task_jzq_y3z_wxb__prereq_chm_cjx_3dc"/>

## Prerequisites

-   You must have tenant administrator role to configure connectivity to an SAP Process Orchestration system.

-   You have completed the tasks mentioned in [Importing Content from SAP Process Orchestration System](importing-content-from-sap-process-orchestration-system-53db5fb.md).




<a name="task_jzq_y3z_wxb__context_mnj_rkz_wxb"/>

## Context

Execute the following steps in your SAP BTP subaccount. After you create a destination, an entry for that SAP Process Orchestration system is automatically created in the *System*settings tab and it is ready to use.

Though creating destinations directly in the SAP BTP subaccount is a valid approach, we recommend you to use the *System* settings tab.



<a name="task_jzq_y3z_wxb__steps_nnj_rkz_wxb"/>

## Procedure

1.  Log on to SAP BTP cockpit and navigate to your subaccount.

    In SAP BTP, Destination service is used to store your connectivity configuration.

2.  Navigate to *Connectivity* \> *Destinations* and choose *New Destination*.

    For general information on creating destinations in your subaccount, see [Create a Destination](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/3fa7934f5a714bf88d8490958211382f.html).

3.  Configure a new destination with the following details specific to your system:

    **Integration Directory Destination**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Content
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `PO_<systemname>_DIR`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    `HTTP`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Add a meaningful description
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add your system URL
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    `OnPremise`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    `Basic Authentication`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*
    
    </td>
    <td valign="top">
    
    Add your location ID
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Add the user ID \(technical user\) from your SAP Process Orchestration system

    > ### Note:  
    > The user must be assigned to the following roles in your SAP Process Orchestration system:
    > 
    > -   `SAP_XI_API_DISPLAY_J2EE`
    > -   `SAP_XI_API_DEVELOP_J2EE`
    > -   `SAP_XI_MONITOR_J2EE`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Add the user's password
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Additional Properties:
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *systemname*
    
    </td>
    <td valign="top">
    
    Add the name of the system you created in Migration Assessment
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *esrdestination*
    
    </td>
    <td valign="top">
    
    **Optional**: If you use a central ESR and need to create an ESR destination \(see next step\), add the destination's name here
    
    </td>
    </tr>
    </table>
    
4.  **Optional**: If you're using a central Enterprise Services Repository \(ESR\), create a second destination with the details listed in the following table.

    If you're not using a central ESR, you only need the Integration Directory destination.

    **ESR Destination**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Content
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `PO_<systemname>_ESR`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    `HTTP`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Add a meaningful description
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    Add your system URL
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    `OnPremise`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    `Basic Authentication`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*
    
    </td>
    <td valign="top">
    
    Add your location ID
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Add the user ID \(technical user\) from your SAP Process Orchestration system

    > ### Note:  
    > The user must be assigned to the following roles in your SAP Process Orchestration system:
    > 
    > -   `SAP_XI_API_DISPLAY_J2EE`
    > -   `SAP_XI_API_DEVELOP_J2EE`
    > -   `SAP_XI_MONITOR_J2EE`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Add the user's password
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Additional Properties:
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *systemname*
    
    </td>
    <td valign="top">
    
    Add the name of the system you created in Migration Assessment
    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*.


