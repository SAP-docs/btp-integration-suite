<!-- loioe1af62b58a674149bc734414cce04a5a -->

# SAP S/4HANA

As an administrator for SAP S/4HANA, you need to configure the communication between Graph and SAP S/4HANA by installing a cloud connector and creating destinations.



<a name="loioe1af62b58a674149bc734414cce04a5a__section_sfb_hhx_qpb"/>

## Setup Connectivity

As the Cloud Connector administrator, you must install a cloud connector on your business system.



### Prerequisites

Your SAP BTP Administrator has provided the following:

-   Region

-   Subaccount

-   Assigned a Cloud Connector administrator to a role or role collections . For more information, see [Initial Configuration](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/db9170a7d97610148537d5a84bf79ba2.html).




### Procedure

1.  Install and configure the cloud connector. For more information, see [Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html).

2.  Add the SAP BTP subaccount to the cloud connector. For more information, see [Manage Subaccounts](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/f16df12fab9f4fe1b8a4122f0fd54b6e.html).




### Establish Trust

1.  Configure the single-sign on \(SSO\) Identity Authentication Service
2.  Upload your key-pair keystore in SAP BTP cockpit. Otherwise, use the default key-pair keystore.

3.  Set up the SAP S/4HANA side.
4.  Set up the SAP BTP side.

For a detailed description of each of these steps, see [Authenticating Users against On-Premise Systems](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/authenticating-users-against-on-premise-systems?version=Cloud).



<a name="loioe1af62b58a674149bc734414cce04a5a__section_qzs_3b5_vxb"/>

## Create Destinations

As the SAP BTP administrator, you must create and configure an HTTP destination that either supports principal propagation or is based on a technical user.



### Destination for Identity Propagation

**Prerequisites**

-   Cloud Connector administrator has added the SAP BTP subaccount to the cloud connector.

-   To configure the HTTP destination, you need to know the following:

    -   Host and port of the system exposed by the cloud connector

    -   Authentication type

    -   Location ID \(if configured in the cloud connector\)

    -   SAP S/4HANA tenant ID



**Procedure**

Create a *PrincipalPropagation* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit *Connectivity* \> *Destinations*, and choose *New Destination*. Enter the following:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    The destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    `HTTP` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Virtual URL of the protected on-premise application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    OnPremise
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    PrincipalPropagation
    
    </td>
    </tr>
    </table>
    
2.  Click *Save*.

To create a destination that uses the host exposed by the cloud connector, make sure that:

-   *Proxy Type* is set to *OnPremise*.

-   *Authentication Type* is supported by your cloud connector configuration. For more information, see [Configuring Principal Propagation](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configuring-principal-propagation?version=Cloud).

-   The SAP S/4HANA tenant ID is configured as an *Additional Property*:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    sap-client
    
    </td>
    <td valign="top">
    
    SAP S/4HANA tenant ID
    
    </td>
    </tr>
    </table>
    

For more information about how to create the destination, see [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/783fa1c418a244d0abb5f153e69ca4ce.html).



### Destination with a Technical User

**Prerequisites**

The SAP S/4HANA administrator configured the communication between Graph and SAP S/4HANA. You know the following:

-   URL of your SAP S/4HANA account

-   Name of the communication \(technical\) user in the SAP S/4HANA tenant

-   Password for the communication user


**Procedure**

Create a *BasicAuthentication* HTTP destination and configure its settings as follows:

1.  Go to SAP BTP cockpit*Connectivity* \> *Destinations* and choose *New Destination*. Enter the following:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter the destination name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    `HTTP` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The service URL from the communication arrangement.

    > ### Note:  
    > Make sure you use the HTTPS protocol.


    
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
    
    `BasicAuthentication` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    The name of the communication user in the SAP S/4HANA tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    The password for the communication user.
    
    </td>
    </tr>
    </table>
    
2.  Click *Save*.


**Related Information**  


[Configure Systems in Cloud Connector](https://developers.sap.com/tutorials/btp-app-ext-service-cloud-connector.html)

