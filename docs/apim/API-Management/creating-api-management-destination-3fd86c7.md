<!-- loio3fd86c7b15b84314a02dc9f0a1ea9938 -->

# Creating API Management Destination

Create destination **APIManagement** in your source subaccount to make API calls for fetching the API content from the API portal workspace.



<a name="loio3fd86c7b15b84314a02dc9f0a1ea9938__prereq_h1c_hz3_v4b"/>

## Prerequisites

Create an instance of API portal, API Management service and fetch the service keys from the service instance as shown in the samplecode. For more information, see[Creating an Instance of API portal, API Management](creating-an-instance-of-api-portal-api-management-6129172.md).

> ### Sample Code:  
> ```
> {
> 	"url": "https://<apiportal application name>.cfapps.sap.hana.ondemand.com",
> 	"tokenUrl": "https://<Space name>.authentication.sap.hana.ondemand.com/oauth/token",
> 	"clientId": "sb-apiaccessxxxxxxxx!xxxx|api-portal-xsuaa!bxxxx",
> 	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxx="
> }
> 
> ```



<a name="loio3fd86c7b15b84314a02dc9f0a1ea9938__steps_nv2_z2d_44b"/>

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
    
    Enter `APIManagement` as the destination name.

    Please note that this value is case-sensitive.
    
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
    
    Provide the URL from the service key details and append `/api/1.0/transportmodule/Transport` to it.
    
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
    
    Provide the client ID from the service key details.
    
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
    
    Provide the URL from the service key details.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*.

    You can also do a *Check Connection* to verify whether you've added the destination correctly. Once you perform a check connection, the following pop-up message appears: `Connection to "APIManagement" is established.`

    > ### Note:  
    > In case you receive a "401: Unauthorized" response code, please note that its an accepted response code.




<a name="loio3fd86c7b15b84314a02dc9f0a1ea9938__result_j2v_h2w_n4b"/>

## Results

You’ve created the destination *APIManagement*.

