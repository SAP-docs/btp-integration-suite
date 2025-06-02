<!-- copy17ab4a2364e84370bc8dfb042de9f3a1 -->

# Initial Setup

As a Subaccount or Tenant Administrator, you need to add Graph as a capability of API Management within SAP Integration Suite.



<a name="copy17ab4a2364e84370bc8dfb042de9f3a1__section_jkq_dgg_fwb"/>

## Prerequisites

1.  Your SAP BTP Global Account administrator has already created a subaccount. For more information, see [Create a Subaccount](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/05280a123d3044ae97457a25b3013918.html).

2.  The subaccount is in SAP BTP, Cloud Foundry environment with enabled Cloud Foundry.

3.  An SAP Integration Suite entitlement has been created for your subaccount. For more information, see [Configure Entitlements](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/37f8871865114f44aebee3db6ac64b72.html).

4.  You have subscribed to the SAP Integration Suite and assigned the *Integration\_Provisioner* role collection to yourself. You must assign this role to add capabilities, such as API Management and Graph, on the SAP Integration Suite home page.

    For more information, see [Set Up API Management from Integration Suite](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html#0bc64de0-ed01-4d11-a675-6dd6942f909e)\(Steps 1–3\).

5.  You have activated Graph on the SAP Integration Suite home page and assigned yourself to the following Graph role collection:

    -   *Graph.KeyUser*

        When you assign yourself to this role collection, you are automatically assigned to the following roles:

        -   *Graph\_Key\_User*

        -   *Graph\_Navigator\_Viewer*






<a name="copy17ab4a2364e84370bc8dfb042de9f3a1__section_configEntitlement"/>

## 1. Configure Entitlement for Graph

Your global account administrator is responsible for configuring the Graph entitlement as follows:

1.  Go to *Entitlements* in the SAP BTP cockpit.

2.  Choose *Edit* \> *Add Service Plans*.

3.  Search for and choose *SAP Graph* and do the following:

    > ### Note:  
    > Some services are only available in the Cloud Foundry environment, so your subaccount must be Cloud Foundry-enabled.

    1.  *configuration* to configure business data graphs using the Graph Configuration API.

4.  Search for *Process Integration Runtime* and choose the following plan:

    1.  *integration-flow* under the Process Integration Runtime service for business data graph consumption.

        > ### Note:  
        > Do not choose the *api* service plan.


5.  Choose *Add Service Plan* \> *Save*.


For more information on how to create a *Process Integration Runtime* instance, see [Authentication](50-Development/authentication-79aabda.md).



<a name="copy17ab4a2364e84370bc8dfb042de9f3a1__section_AddGraph_APIM"/>

## 2. Activate Graph on SAP Integration Suite 

1.  Go to the *Integration Suite* home page, and under *Capabilities*, choose *Add Capabilities*.
2.  On the *Activate Capabilities* dialog, under *Select Capabilities*, choose *Design, Develop, and Manage APIs* and choose *Next*.
3.  To activate *Graph*, select the following, and choose *Next*:

    1.  *Enable Developer Hub*

    2.  *Graph*


    > ### Note:  
    > If you have already set up API Management, choose *Edit*, and select *Graph*. You must select **Enable Developer Hub** to activate *Graph*.

4.  Choose *Activate* and once the status on the *Summary* changes from *In Progress* to *Active*, choose *OK*.



<a name="copy17ab4a2364e84370bc8dfb042de9f3a1__section_DefineUsers"/>

## 3. Define Users for Graph

Graph doesn't manage user identities and it can't directly authenticate clients. Instead, it relies on the SAP Authorization and Trust Management service.

There are two ways to define users:

-   Add users, one-by-one, for the purpose of bootstraps, demos, and proofs of concepts \(PoCs\) to the SAP BTP subaccount \(for example, via the SAP BTP cockpit\).

-   Use your own user base and Identity Provider \(IdP\). For this, you must establish a trust relationship with a SAML 2.0 IdP in your subaccount.

    For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/cb1bc8f1bd5c482e891063960d7acd78.html).


Once you enable Graph, you see all of the Graph role collections in your list.



### Enable Graph Users

-   Graph Key User

    The creation and activation of business data graphs is managed by a user with a special role, the *Graph\_Key\_User* authorization role. You must assign this role to one or more users so that they can create and activate business data graphs for a landscape.

    To assign the *Graph.KeyUser* role collection to a user, do the following:

    1.  In the SAP BTP cockpit, go to *Security* \> *Users*.

    2.  Select the relevant user. Under *Role Collections*, choose *Assign Role Collection*.

    3.  Search for *Graph.KeyUser*, select the role collection, and choose *Assign Role Collection*.

    4.  To apply the role, go back to the SAP Integration Suite home page.


-   Graph Navigator Viewer

    Graph Navigator is a tool in Developer Hub that developers use to inspect business data graphs. For more information, see [Graph Navigator on Developer Hub](50-Development/graph-navigator-on-developer-hub-8e75d31.md).

    To assign the *GraphNavigator.Viewer* role collection to a user with the *Graph\_Navigator\_Viewer* role, do the following:

    1.  In the SAP BTP cockpit, go to *Security* \> *Users*.

    2.  Select the relevant user. Under *Role Collections*, choose *Assign Role Collection*.

    3.  Search for *GraphNavigator.Viewer*, select the role collection, and choose *Assign Role Collection*.

    4.  To apply the role, go back to the SAP Integration Suite home page.


-   Graph Guest

    There are cases where you need users to have read-only access to Graph. Assign the *Graph\_Guest* authorization role to one or more users so that they have read-only access to Graph and the Graph Configuration API.

    1.  In the SAP BTP cockpit, go to *Security* \> *Users*.

    2.  Select the relevant user. Under *Role Collections*, choose *Assign Role Collection*.

    3.  Search for *Graph.Guest*, select the role collection, and choose *Assign Role Collection*.

    4.  To apply the role, go back to the SAP Integration Suite home page.



> ### Note:  
> Reselect your subaccount to access *Users* after assigning the role collection.

For more information, see:

-   [Define a Role Collection](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4b20383efab341f181becf0a947a5498.html) 
-   [Add Roles to a Role Collection](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e3130fb95aa64970b07d4dc65b24df1a.html) 
-   [Assign Users to Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c5766765bda74ad59fe656977c8fa4d6.html) 

