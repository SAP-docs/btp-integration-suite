<!-- loio3a6a81e12df04fa790770bdc25e7ddff -->

# Creating Content Assembly Service Destination

Create destination **ContentAssemblyService** in source subaccount to make API calls to the Content Assembly Service.



<a name="loio3a6a81e12df04fa790770bdc25e7ddff__prereq_cbq_pk3_v4b"/>

## Prerequisites

Create an instance of Content Agent and fetch the service keys. For more information, see [Creating an Instance of Content Agent](creating-an-instance-of-content-agent-359ecd7.md).



## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your source subaccount.

2.  Choose the *Destinations* tab in the left-hand pane.

3.  Choose *New Destination*.

4.  In *Destination Configuration* section, provide values in fields based on description in table.


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

    Provide value as ***ContentAssemblyService***.

    Please note that this value is case-sensitive.


    
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

    Provide the URL from the service key details.


    
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

    OAuth2ClientCredentials


    
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

    > ### Note:  
    > Append the value oauth/token to the *Token Service URL*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Token Service User


    
    </td>
    <td valign="top">

    No inputs required.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Token Service Password


    
    </td>
    <td valign="top">

    No inputs required.


    
    </td>
    </tr>
    </table>
    
5.  Choose *Save*.

    You can also do a *Check Connection* to verify whether you've added the destination correctly. Once you perform a check connection, the following pop-up message appears: ***Connection to "ContentAssemblyService" is established. Response returned: "401: Unauthorized"***

    > ### Note:  
    > In this case, 401 is an accepted response code.




<a name="loio3a6a81e12df04fa790770bdc25e7ddff__result_j2v_h2w_n4b"/>

## Results

You’ve created the destination *ContentAssemblyService*.

