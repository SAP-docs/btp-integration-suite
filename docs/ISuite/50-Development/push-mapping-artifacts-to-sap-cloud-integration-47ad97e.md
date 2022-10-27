<!-- loio47ad97e5b7614715ac54dcb24d72a871 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Push Mapping Artifacts to SAP Cloud Integration

You can inject mapping artifacts from Integration Advisor to your SAP Cloud Integration tenant.



## Context

You need to maintain the SAP Cloud Integration tenant details into which you need to inject the resources under the *Destinations* tab of your subaccount in .

1.  Login to and navigate to your subaccount.

2.  Choose *Destinations**New Destination*.
3.  Provide the details of your SAP Cloud Integration tenant under from the left pane and select *Destination Configuration*.


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

    from the left pane and selectEnter a valid name for your destination. This field is case-sensitive.

    > ### Note:  
    > The destination name must start with the prefix ***CPI\_TENANT\_***.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Type


    
    </td>
    <td valign="top">

    HTTP


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Description


    
    </td>
    <td valign="top">

    You can provide a description for your reference. This field is optional.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    URL


    
    </td>
    <td valign="top">

    For Neo environment, enter the TMN URL of the SAP Cloud Integration tenant.

    For CF, enter the design time URL of the SAP Cloud Integration tenant.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Proxy Type


    
    </td>
    <td valign="top">

    Internet


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Authentication


    
    </td>
    <td valign="top">

    Enter the authentication details.

    > ### Note:  
    > The supported authentication modes are:
    > 
    > -   BasicAuthentication : Maintain the *User* and *Password* fields.
    > 
    > -   OAuth2ClientCredentials : Maintain the following fields
    > 
    >     -   Client ID
    > 
    >     -   Client Secret
    >     -   Token Service URL
    > 
    >     Maintain the following fields if you are working in Neo environment:
    > 
    >     -   Token Service User : Same value as *Client ID*
    >     -   Token Service Password : Same value as *Client Secret*
    > 
    >     You need to register the client application as the OAuth client in the consumer account using the with the TMN node details. In the *Security* \> *OAuth* section, go to the *Clients* tab. Under *Subscription*, enter the VM name of the TMN node\(it ends with the node type `.tmn`\).
    > 
    >     For information on creating OAuuth client credentials for Neo environment, see: [Creating OAuth Client Credentials for Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/040d8110293d44b1bfaa75674530d395.html "The API is protected by basic authentication and OAuth.") :arrow_upper_right:
    > 
    >     For information on creating OAuth client credentials for Cloud Foundry, see: [Creating OAuth Client Credentials for Cloud Foundry Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/50b63c69028643b18016d6795003392d.html "You can create OAuth client credentials to access your SAP Cloud Integration tenant hosted on the Cloud Foundry environment.") :arrow_upper_right:.


    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.



## Procedure

1.  Access the Mapping Guideline \(MAG\) section.

2.  Select the MAG from which you want to inject the mapping artifacts.

3.  Choose <span class="SAP-icons"></span> and then choose *Inject* \> *SAP Cloud Integration Flow Resources*.

4.  Choose an SAP Cloud Integration tenant from the *Destinations* list.

5.  The next step *2 Integration Package* lists down the integration packages available under the tenant that you chose in the previous step. Choose the desired integration package from the list.

    Configure-only packages will not be listed in this step.

6.  On selecting the package, the next step displays the list of integration flows available under that package. Select an integration flow from the list into which you want to inject the resources and choose *Inject*.

7.  The *Summary* step provides the following information:

    1.  *Status* to show if the injection was successful

    2.  Package Name

    3.  Integration Flow

        If the resource injection is successful, you can navigate to the integration flow directly from the *Summary* step using the hyperlink provided under the *Integration Flow* field.

    4.  List of *Resources Injected* into the integration flow


8.  Choose *Close* after reviewing the details.


