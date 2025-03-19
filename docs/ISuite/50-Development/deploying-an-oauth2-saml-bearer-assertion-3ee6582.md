<!-- loio3ee658286bac40829fcfa4e0c9044f75 -->

# Deploying an OAuth2 SAML Bearer Assertion

Many web servers use OAuth 2.0 for authorization purposes. If you want to connect to a system that uses OAuth 2.0 authentication, you need to deploy an OAuth2 Credentials artifact using the following procedure.



<a name="loio3ee658286bac40829fcfa4e0c9044f75__prereq_f5s_4px_1pb"/>

## Prerequisites

For technical user propagation workflow, you've created a key pair. See [Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md).



<a name="loio3ee658286bac40829fcfa4e0c9044f75__context_q5p_c51_lmb"/>

## Context

You can design your OAuth2 credential either via principal propagation or technical user propagation.

-   Using principal propagation, you forward the identity of the logged-in user to the target OAuth2-supported system. This method works well during the runtime \(execution\) of integration artifacts.

-   Using technical user propagation, you propagate a dedicated technical user profile mentioned in the key-pair common name as the principal to your target system. Currently, this method works with SuccesFactors OData V2 Receiver, SuccesFactors SOAP Sender, and SuccesFactors SOAP Receiver Adapters. Especially, in the query modeler, use technical user propagation. To know more about how to implement technical user propagation, read the [blog](https://blogs.sap.com/2021/03/26/sap-cloud-integration-oauth2-saml-bearer-x.509-certificate-authentication-support-in-successfactors-connector/).


> ### Note:  
> Read [SAP Cloud Integration – Principal Propagation with SuccessFactors OData V2](https://blogs.sap.com/2018/07/30/sap-cloud-platform-integration-principal-propagation-with-successfactors-odata-v2/), to understand how to design, and deploy an integration flow that communicates to SuccessFactors OData V2 endpoint with OAuth2 authentication.

More information on OAuth: [https://tools.ietf.org/html/rfc6749](https://tools.ietf.org/html/rfc6749).



<a name="loio3ee658286bac40829fcfa4e0c9044f75__steps_r5p_c51_lmb"/>

## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](../manage-security-for-edge-integration-cell-1783cf8.md).

3.  Click the *Security Material* tile in the *Manage Security* section.

4.  Choose *Add*.

5.  As *Type*, select *OAuth2 SAML Bearer Assertion*.

6.  Specify the following attributes:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
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
    
    Name for the artifact that you want to deploy on the tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Description of the artifact name you're deploying on the tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    Provide the host name of the target system, to which you want to establish the connection.

    > ### Example:  
    > `www.successfactors.com`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    A unique identifier created by the target system to identify the client.

    -   For fetching a client key for SuccessFactors, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html).


    > ### Note:  
    > Every time you edit an OAuth2 credentials artifact, you must re-enter the client key.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Provide the URL that generates OAuth2 token for the registered OAuth2 client.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target System Type
    
    </td>
    <td valign="top">
    
    Specify the relevant host system for authenticating the user against the system. Select one of the following systems :

    -   SuccessFactors

    -   SAP BTP \(Neo\)

    -   SAP BTP \(CF\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Company ID

    \(only if you select *SuccessFactors* for target system type\)
    
    </td>
    <td valign="top">
    
    Specify the company ID of your SuccessFactors instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User ID

    \(only if you select *SuccessFactors* for target system type\)
    
    </td>
    <td valign="top">
    
    Choose one of the following:

    -   Principal Propagation

    -   Key Pair Common Name \(CN\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Additional Properties

    \(only if you select *SuccessFactors* for target system type and *Principal Propagation* for user ID\)
    
    </td>
    <td valign="top">
    
    Maintain the *Value* of the key field *userIdSource* for each environment as follows:

    -   If your tenant is on Neo environment, set the value as **mail.**
    -   If your tenant is on Cloud Foundry environment, set the value as **email.**


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Pair Alias

    \(only if you select *SuccessFactors* for target system type and *Key Pair Common Name \(CN\)* for user ID\)
    
    </td>
    <td valign="top">
    
    Provide the alias name that you defined in the prerequisites.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service User

    \(only if you select SAP BTP for target system type\)
    
    </td>
    <td valign="top">
    
    Username required to access the *Token Service URL*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service Password

    \(only if you select SAP BTP for target system type\)
    
    </td>
    <td valign="top">
    
    Password required to access the *Token Service URL*.
    
    </td>
    </tr>
    </table>
    
7.  Choose *Deploy*.


**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

