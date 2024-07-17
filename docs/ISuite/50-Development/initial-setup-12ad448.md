<!-- loio12ad448225ac47049982d9faab7978a3 -->

# Initial Setup

As a Subaccount or Tenant Administrator, you need to add Graph as a capability of API Management within SAP Integration Suite.



<a name="loio12ad448225ac47049982d9faab7978a3__section_jkq_dgg_fwb"/>

## Prerequisites

1.  Your SAP BTP Global Account administrator has already created a subaccount. For more information, see [Create a Subaccount.](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/05280a123d3044ae97457a25b3013918.html)

2.  An SAP Integration Suite entitlement has been created for your subaccount. For more information, see [Configure Entitlements](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/37f8871865114f44aebee3db6ac64b72.html).

3.  You have subscribed to the SAP Integration Suite and assigned the *Integration\_Provisioner* role collection to yourself. You must assign this role to add capabilities, such as API Management and Graph, on the Integration Suite home page.

    For more information, see [Set Up API Management from Integration Suite](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html#0bc64de0-ed01-4d11-a675-6dd6942f909e)\(Steps 1–3\).

4.  You have activated Graph on the Integration Suite home page and assigned yourself to the following Graph role collection:

    -   *Graph.KeyUser*

        When you assign yourself to this role collection, you are automatically assigned to the following roles:

        -   *Graph\_Key\_User*

        -   *Graph\_Navigator\_Viewer*






<a name="loio12ad448225ac47049982d9faab7978a3__section_configEntitlement"/>

## 1. Configure Entitlement for Graph

Your global account administrator is responsible for configuring the Graph entitlement as follows:

1.  Go to *Entitlements* in the SAP BTP cockpit.

2.  Choose *Configure Entitlements* \> *Add Service Plans*.

3.  Search for and choose *SAP Graph* and do the following:

    1.  Choose one or more of the following plans:

        -   *api* for business data graph consumption

        -   *configuration* to configure business data graphs using the Graph Configuration API.


    2.  Choose *Add Service Plan*.

    3.  Choose *Save*.





<a name="loio12ad448225ac47049982d9faab7978a3__section_AddGraph_APIM"/>

## 2. Configure Graph

1.  Go to the *Integration Suite* home page, and under *Capabilities*, choose *Add Capabilities*.
2.  On the *Activate Capabilities* dialog, under *Select Capabilities*, choose *Design, Develop, and Manage APIs* and choose *Next*.
3.  To activate *Graph*, select the following, and choose *Next*:

    1.  *Enable SAP API Business Hub Enterprise*

    2.  *Graph*

    > ### Note:  
    > If you have already set up API Management, choose *Edit*, and select *Graph*. You must select *SAP API Business Hub Enterprise* to activate *Graph*.

4.  Choose *Activate* and once the status on the *Summary* changes from *In Progress* to *Active*, choose *OK*.



<a name="loio12ad448225ac47049982d9faab7978a3__section_DefineUsers"/>

## 3. Define Users for Graph

Graph doesn't manage user identities and it can't directly authenticate clients. Instead, it relies on XSUAA, the SAP Authorization and Trust Management Service.

There are two ways to define users:

-   Add users, one-by-one, for the purpose of bootstraps, demos, and proofs of concepts \(PoCs\) to the SAP BTP subaccount \(for example, via the SAP BTP cockpit\).

-   Use your own user base and Identity Provider \(IdP\). For this, you must establish a trust relationship with a SAML 2.0 IdP in your subaccount.

    For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/cb1bc8f1bd5c482e891063960d7acd78.html).


Once you enable Graph, you see both Graph role collections in your list.



### Enable Graph Users

-   Graph Key User

    The creation and activation of business data graphs is managed by a user with a special role, the *Graph\_Key\_User* authorization role. You must assign this role to one or more users so that they can create and activate business data graphs for a landscape.

    To assign the *Graph.KeyUser* role collection to a user, do the following:

    1.  In the SAP BTP cockpit, go to *Security* \> *Users*.

    2.  Select the relevant user. Under *Role Collections*, choose *Assign Role Collection*.

    3.  Search for *Graph.KeyUser*, select the role collection, and choose *Assign Role Collection*.

    4.  To apply the role, go back to the Integration Suite home page.


-   Graph Navigator Viewer

    Graph Navigator is a tool in SAP API business hub enterprise that developers use to inspect business data graphs. For more information, see [Graph Navigator in SAP API Business Hub Enterprise](graph-navigator-in-sap-api-business-hub-enterprise-8e75d31.md).

    To assign the *GraphNavigator.Viewer* role collection to a user with the *Graph\_Navigator\_Viewer* role, do the following:

    1.  In the SAP BTP cockpit, go to *Security* \> *Users*.

    2.  Select the relevant user. Under *Role Collections*, choose *Assign Role Collection*.

    3.  Search for *GraphNavigator.Viewer*, select the role collection, and choose *Assign Role Collection*.

    4.  To apply the role, go back to the Integration Suite home page.



> ### Note:  
> Reselect your subaccount to access *Users* after assigning the role collection.

For more information, see:

-   [Define a Role Collection](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4b20383efab341f181becf0a947a5498.html) 
-   [Add Roles to a Role Collection](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e3130fb95aa64970b07d4dc65b24df1a.html) 
-   [Assign Users to Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c5766765bda74ad59fe656977c8fa4d6.html) 

