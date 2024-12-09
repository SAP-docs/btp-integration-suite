<!-- loiob46816c20e02415597d5546b1e277e23 -->

# Runtime Access and Role Assignment for OData Provisioning

Steps to complete the activation of the OData Provisioning capability by providing runtime access and assigning roles.





### Before you begin:

-   You've subscribed to SAP Integration Suite. You have the*Integration\_Provisioner*role and can access the Integration Suite. See [Subscribing and Configuring Initial Access to SAP Integration Suite](10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md).
-   You've activated the OData Provisioning capability. See [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md).
-   You additionally need the role of org member and space developer in the Cloud Foundry space in which the Integration Suite is provisioned.

After you activate the OData Provisioning capability, you need to:

-   Create a service instance to get runtime access to registered services
-   Create a service key for the service instance
-   Assign required roles



<a name="loiob46816c20e02415597d5546b1e277e23__section_hjm_4sx_ncc"/>

## Creating a Service Instance and Service Key

> ### Tip:  
> If you created a service instance and service key when using OData Provisioning as a part of the SAP BTP, serverless runtime service, you can reuse them if you've subscribed to SAP Integration Suite on the same subaccount.



### Service Instance Creation

After subscribing to the SAP Integration Suite, and activating the OData Provisioning capability, you can create the service instance as follows:

1.  Navigate to your subaccount in the SAP BTP cockpit.
2.  From the left navigation panel, navigate to *Services* \> *Instances and Subscriptions*.
3.  Choose *Create*.
4.  Choose *Serverless Runtime* \(xfs-runtime\) as the service, and then choose the default plan and Cloud Foundry space.
5.  Enter an instance name, then choose *Next*.
6.  Choose *Create*.



### Service Key Creation

To create the service key, do the following:

1.  Choose the service instance that you created.
2.  In the right-hand pane, navigate to *Service Keys* \> *Create Service Key*.
3.  In the *Create Service Key* dialog, provide a *Name*.
4.  In the *Configure Binding Parameters* field, choose *JSON* and enter one of the following payloads as per your requirement:

    ****


    <table>
    <tr>
    <th valign="top">

    To create a service key of type:
    
    </th>
    <th valign="top">

    Use payload...
    
    </th>
    <th valign="top">

    Security
    
    </th>
    <th valign="top">

    Sample of generated credentials
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Binding Secret
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Low
    
    </td>
    <td valign="top">
    
    > ### Sample Code:  
    > ```
    > {
    >     "credentials": {
    >         "xsappname": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx!xxxxxxx|xfsrt-service-broker!xxxxxxx",
    >         "client_id": "xx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxx!xxxxxxx|xfsrt-service-broker!xxxxxxx",
    >         "client_secret": "xxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx=",
    >         "grant_type": "client_credentials",
    >         "token_url": "https://aws-eu12-odp-dev-xx.authentication.euxx.hana.ondemand.com/oauth/token"
    >     },
    >     "uri": "https://services.odp.cfapps.<region>.hana.ondemand.com"
    > }
    > ```


    
    </td>
    </tr>
    </table>
    
5.  Click *Save*. The credentials generated as part of the service key creation can be used for the runtime access of the registered OData services.



<a name="loiob46816c20e02415597d5546b1e277e23__section_zq2_vdh_rcc"/>

## Assign Roles

You create a role collection and add roles for OData Provisioning, see [Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection). Then assign this role collection to the users who have to access and work with the OData Provisioning capability.

1.  Navigate to the subaccount where you've subscribed to Integration Suite on the SAP BTP Cockpit and add the following roles to a role collection:
    -   *ODPManage*: View and register OData services. Monitor errors, manage metadata validation and cache settings.
    -   *ODPAPIAccess*: Provides access to the service document. You can access the service document from a link against each of the registered OData services.
    -   *APIFullAccess*: Provides runtime access to the registered OData services.

2.  To assign these roles:

    1.  Choose *Security* \> *Users* from the left navigation pane.
    2.  Select the username, and under the *Role Collections* section, choose *Assign Role Collection*.
    3.  In the dialog box that opens, select the role collection that you created, and choose *Assign Role Collection*.


