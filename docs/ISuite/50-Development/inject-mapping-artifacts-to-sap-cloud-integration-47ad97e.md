<!-- loio47ad97e5b7614715ac54dcb24d72a871 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Inject Mapping Artifacts to SAP Cloud Integration

You can inject mapping artifacts from Integration Advisor to your SAP Cloud Integration tenant.



## Context

You need to maintain the SAP Cloud Integration tenant details into which you need to inject the resources under the *Destinations* tab of your subaccount in SAP BTP cockpit.

> ### Note:  
> Users leveraging Integration Advisor within SAP Integration Suite do not need to manually maintain destination details, as the capability automatically discovers the target Cloud Integration tenant.
> 
> However, if you plan to inject resources into a Cloud Integration tenant outside your SAP Integration Suite subscription, you must manually configure the destination details. For such cases, follow the procedure below.

1.  Login to SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Destinations* \> *New Destination*.
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
    
    Enter a valid name for your destination. This field is case-sensitive.

    > ### Note:  
    > The destination name must start with the prefix `CPI_TENANT_`.


    
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

    For CF, copy the url from the service key of the*Process Integration Runtime*service instance and paste it in the *URL* field.
    
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
    > -   OAuth2ClientCredentials : Maintain the following fields for CF
    > 
    >     -   *Client ID*: Copy the value from the `clientid` field of the service key created for Process Integration Runtime service instance and paste it in this field.
    > 
    >     -   *Client Secret*: Copy the value from the `clientsecret` field from the service key created for Process Integration Runtime service instance and paste it in the field.
    >     -   *Token Service URL*: Copy the value from the `tokenurl` field from the service key created for Process Integration Runtime service instance and paste it in the field.
    > 
    >     Maintain the following fields if you are working in Neo environment:
    > 
    >     -   Token Service User : Same value as *Client ID*
    >     -   Token Service Password : Same value as *Client Secret*
    > 
    >     You need to register the client application as the OAuth client in the consumer account using the SAP BTP cockpit with the TMN node details. In the *Security* \> *OAuth* section, go to the *Clients* tab. Under *Subscription*, enter the VM name of the TMN node\(it ends with the node type `.tmn`\).
    > 
    >     For information on creating OAuth client credentials for Cloud Foundry, see: [Creating OAuth Client Credentials for Cloud Foundry Environment](creating-oauth-client-credentials-for-cloud-foundry-environment-50b63c6.md).


    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.



## Procedure

1.  Access the Mapping Guideline \(MAG\) section.

2.  Select the MAG from which you want to inject the mapping artifacts.

3.  Choose <span class="SAP-icons-V5"></span> and then choose *Inject* \> *SAP Cloud Integration Flow Resources*.

4.  Choose an SAP Cloud Integration tenant from the *Connections* list.

    The *Connections* table displays two sections:

    1.  *Built-In*: Displays the Cloud Integration tenant associated with your SAP Integration Suite subscription.

    2.  *User-Defined*: Displays manually created destinations by the user, typically used for external Cloud Integration tenants or custom integrations.

5.  The next step *2 Integration Package* lists down the integration packages available under the tenant that you chose in the previous step. Choose the desired integration package from the list.

    Configure-only packages will not be listed in this step.

6.  On selecting the package, the next step displays the list of integration flows available under that package. Select an integration flow from the list into which you want to inject the resources and choose *Inject*.

7.  The *Result* step provides the following information:

    1.  *Status* to show if the injection was successful

    2.  Package Name

    3.  Integration Flow

        If the resource injection is successful, you can navigate to the integration flow directly from the *Summary* step using the hyperlink provided under the *Integration Flow* field.

    4.  List of *Resources Injected* into the integration flow


8.  Choose *Close* after reviewing the details.


