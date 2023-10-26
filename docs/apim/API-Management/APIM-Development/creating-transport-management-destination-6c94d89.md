<!-- loio6c94d899f7c448d0a4bdb47e48fc9420 -->

# Creating Transport Management Destination

Create destination **TransportManagement** in your source subaccount to make API calls to the SAP Cloud Transport Management service \(TMS\).



<a name="loio6c94d899f7c448d0a4bdb47e48fc9420__prereq_akm_1dj_v4b"/>

## Prerequisites

Create an instance of SAP Cloud Transport Management service and fetch the service keys from the service instance as shown in the sample code. For more information, see[Creating an Instance of SAP Cloud Transport Management Service](creating-an-instance-of-sap-cloud-transport-management-service-69a41e2.md).

> ### Sample Code:  
> ```
> {
> "uaa": {
> "clientid": "sb-ebxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx!bxxxx|alm-ts-backend!bxxx",
> "clientsecret": "xxxxxxxxxxxxxxxxxxxxxxx=",
> "url": "https://<Space name>.authentication.sap.hana.ondemand.com",
> "identityzone": "<Space name>",
> "identityzoneid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
> "tenantid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
> "tenantmode": "dedicated",
> "sburl": "https://internal-xsuaa.authentication.sap.hana.ondemand.com",
> "apiurl": "https://api.authentication.sap.hana.ondemand.com",
> "verificationkey": "-----BEGIN PUBLIC KEY-----xxxxxxxxxx-----END PUBLIC KEY-----",
> "xsappname": "xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx!bxxxxx|alm-ts-backend!bxxx",
> "subaccountid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
> "uaadomain": "authentication.sap.hana.ondemand.com",
> "zoneid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
> },
> "uri": "https://transport-service-app-backend.ts.cfapps.sap.hana.ondemand.com"
> }
> ```



<a name="loio6c94d899f7c448d0a4bdb47e48fc9420__steps_nv2_z2d_44b"/>

## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  Choose the *Destinations* tab in the left-hand pane.

3.  Choose *New Destination*.

4.  In *Destination Configuration* section, provide values in fields based on description in table.

    > ### Note:  
    > Use the Client ID, Client Secret, and the Token Service URL from the Prerequisite section.


    <table>
    <tr>
    <th valign="top">

    Fields
    
    </th>
    <th valign="top">

    Details
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter `TransportManagementService` as the destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Enter `HTTP` as the supported type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Enter a brief description stating the purpose of creating a new destination in the *Description* field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Provide the URL from the service key details of the SAP Cloud Transport Management service plan.
    
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
    
    Select the authentication type as `OAuth2ClientCredentials`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    Provide the client ID from the service key details of the SAP Cloud Transport Management service plan.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    Enter the client secret.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Navigate to the SAP Cloud Transport Management Service instance and copy the token service URL from the service key details and append `/oauth/token` to it.
    
    </td>
    </tr>
    </table>
    
5.  Add an additional property to the SAP Cloud Transport Management service by choosing *Edit* \> *New Property*.

    Add `sourceSystemId` in the first text box.

    > ### Note:  
    > While entering the sourceSystemId in the first text box, don't change the case of the text `sourceSystemId`.

    Enter the source node that you created in the Transport Management Applications in the second text box. See [Adding a Source Node in Transport Management Applications](adding-a-source-node-in-transport-management-applications-dc24ea2.md) for the steps on how to add a Source node.

6.  Choose *Save*.

    You can also do a *Check Connection* to verify whether you've added the destination correctly. Once you perform a check connection, the following pop-up message appears: `Connection to "TransportManagementService" is established.`

    > ### Note:  
    > In case you receive a "401: Unauthorized" response code, please note that its an accepted response code.




<a name="loio6c94d899f7c448d0a4bdb47e48fc9420__result_j2v_h2w_n4b"/>

## Results

You’ve created the destination *TransportManagement*.

