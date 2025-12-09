<!-- loioc6fcf31776ff42f98ac45734b00aadf6 -->

# Generating ABAP Proxy

Proxy generation converts non-language-specific interface descriptions in Web Services Description Language \(WSDL\) into executable interfaces known as Proxies. It is now possible to generate ABAP Proxies in SAP Backend systems or S/4 Systems by connecting the SAP Backend to SAP Integration Suite tenant.



<a name="loioc6fcf31776ff42f98ac45734b00aadf6__prereq_qvj_2hf_cgc"/>

## Prerequisites

-   All service interface artifacts must already be imported in SAP Integration Suite tenant. An integration package must not contain duplicate artifacts relevant for proxy generation.
-   You've the `PI_Integration_Developer` role collection assigned. This role collection already has the required `AuthGroup_IntegrationDeveloper` role. See [Managing User Roles](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-user-roles?version) and [Tasks and Permissions for Cloud Integration](https://help.sap.com/docs/integration-suite/sap-integration-suite/tasks-and-permissions-556d5575d4b0483e85d4f3251f21d0ec?)




## Context

> ### Note:  
> If you have imported the objects from Process Orchestration system which was originially used to generate the proxies, you need not generate the proxies again.

The procedure to generate ABAP proxies is essentially the same for each type of proxy. There are two main steps:

-   Select the objects to be called or implemented.
-   Generate and activate the proxies.



## Procedure

1.  Connect to SAP Integration Suite from ABAP Backend system or S/4 System: To connect to an SAP Integration Suite tenant, configure the *RFC destination SAP\_PROXY\_ESR*. This RFC destination is used by proxy generation transaction *SPROXY*. Perform the following steps:

    1.  Start transaction SM59.

        An overview of RFC connections is displayed.

    2.  Expand *RFC Connection* \> *HTTP Connection to Enternal Server of Type G* and look for RFC destination with name *SAP\_PROXY\_ESR*.

    3.  Choose *Create* if the RFC Destination with name *SAP\_PROXY\_ESR* doesn't exist.

    4.  Specify the following information:

        **RFC Destination Settings**


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
        
        RFC Destination
        
        </td>
        <td valign="top">
        
        SAP\_PROXY\_ESR. This is auto-populated if the destination already exists. If you have created a new destination, specify it as *SAP\_PROXY\_ESR*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Connection Type
        
        </td>
        <td valign="top">
        
        HTTP Connection to External Server. This is auto-populated.
        
        </td>
        </tr>
        <tr>
        <td valign="top" colspan="2">
        
        Technical Settings
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Host
        
        </td>
        <td valign="top">
        
        Enter the host URL.

        > ### Note:  
        > For SAP Integration Suite you can find it from BTP Cockpit.
        > 
        > 1.  Navigate to *BTP Cockpit* \> *Instances and Subscriptions* \> *< your instance with api-plan \>* \> *View Credentials \(in JSON format\)*. See [Creating Service Instance and Service Key for Inbound Authentication](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-service-instance-and-service-key-for-inbound-authentication?version=CLOUD)
        > 2.  Use this URL as the host URL.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Path Prefix
        
        </td>
        <td valign="top">
        
        Enter the following:

        > ### Source Code:  
        > ```
        > /rest/api/v1/workspace/sproxy
        > ```


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Host Port
        
        </td>
        <td valign="top">
        
        443
        
        </td>
        </tr>
        </table>
        
    5.  On the *Logon & Security* tab, specify the following:

        **Logon & Security**


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
        
        Basic Authentication
        
        </td>
        <td valign="top">
        
        Choose this option as it is the only option supported for ABAP backend.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        User
        
        </td>
        <td valign="top">
        
        Enter the user to access SAP Integration Suite tenant with the assigned role of `AuthGroup_IntegrationDeveloper` 
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Password
        
        </td>
        <td valign="top">
        
        Enter your SAP Integration Suite tenant password
        
        </td>
        </tr>
        </table>
        
    6.  On the *Security* tab, specify the following *Security Options*:

        **Logon & Security**


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
        
        SSL
        
        </td>
        <td valign="top">
        
        This should be active
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        SSL Certificate
        
        </td>
        <td valign="top">
        
        Select an option where the Integration Suite Client certificate is uploaded. Use Transaction STRUST to upload the SAP Integration Suite tenant certificate.
        
        </td>
        </tr>
        </table>
        
    7.  Save your changes.

    8.  Perform connection test to check if the connection to the tenant can be established successfully.


2.  Generate ABAP proxy: Proxies are generated in the ABAP back-end system, in which the object will subsequently be provided. Login to the system in which you want to generate the proxy and follow the steps below:

    1.  Start the *Enterprise Services Repository Browser*. Use transaction code *SPROXY*.

        The top-level nodes of the tree \(SWCs\) represent the integration packages.

        .

        > ### Note:  
        > Only the integration packages that contain at least one of the proxy relevant artifacts \(Datatypes, Message types, Fault Message types, Service Interfaces\) are listed.

    2.  Expand the nodes of the integration package and the namespace within which you want to generate a proxy.

        > ### Note:  
        > The node of integration package lists the namespaces available for that integration package. Under a namespace, you can view the list of all available objects as well as objects of each type grouped in a separate node like message type or data type. Expand a object type node to display all the objects of that type.

    3.  Select an object.
    4.  To generate the proxy, choose *Generate* from the context menu.
    5.  Specify a package and choose *Enter*.

        Based on the prefix that you specify, valid ABAP names are proposed. You can change the proposed names as required. When the proxy is generated, all the following objects will also be generated:

        Information about the generated proxy interface such as the implementing proxy class, and the generated service definition is displayed in the *Properties* tab.

        The prefix you specified is displayed as part of the ABAP name in the *Properties* tab and also in the *Structure* tab.

        The *External* view and *Internal* view tabs respectively show the operations and methods, and the corresponding ABAP message types and data types.

    6.  Activate the proxy.

        When the proxy is activated, all the underlying objects are automatically activated as well.

        > ### Note:  
        > The ABAP objects such as the class, interface, DDIC type are not created in the system until you activate the proxy.

    7.  Use transaction SE09 to release the transport request.



