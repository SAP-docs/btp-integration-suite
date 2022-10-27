<!-- loio57f104d5b6064720bdca826c6698d34c -->

# Basic Authentication of an IdP User for API Clients

Using this option, the API client is authenticated based on user credentials associated with a user registered at an identity provider \(IdP\).

> ### Caution:  
> This authentication option can’t be used when operating SAP Integration Suite on Alibaba Cloud.
> 
> On Alibaba Cloud, SAP ID Service isn't used as default IdP. Therefore, also basic authentication with SAP ID Service can't be used on Alibaba Cloud.

> ### Note:  
> When setting up trust relationships in SAP BTP cockpit, in most cases *SAP ID service* is used as default identity provider. However, you've the option to define a custom IdP as your default IdP.
> 
> If you like to use SAP Identity Authentication Service as custom IdP, you've to make this IdP as your default IdP. To do that, perform the steps described at [Setting Up SAP Identity Authentication Service as Custom IdP for Basic Authentication](setting-up-sap-identity-authentication-service-as-custom-idp-for-basic-authentication-0668507.md).

The following figure shows the components and the involved security artifacts:

 ![](images/CF_API_BAsic_IdP_e828f5a.png) 

Using SAP BTP cockpit, assign to the user a role that is to be used to authorize the API client to call the OData API. Which role you assign, depends on the Cloud Integration resource you like to access through the API. For more information, see [API Details](../50-Development/api-details-014d6ad.md).

In detail, perform the following steps.

1.  Using SAP BTP cockpit, select your subaccount.

2.  Go to *Security* \> *Role Collections*.

3.  Click the *\+* icon to create a new role collection.

4.  Specify a role collection name \(for example, ***MonitoringAPI***\).

    Let's assume that you want to access monitoring information with the OData API \(using the `MessageProcessingLogs` resource\).

5.  Choose *Create*.

6.  Select the newly created role collection.

7.  Click *Edit*.

8.  In the *Role Name* drop down list, select the role you like to assign.

    Assign a role that grants permission to access certain data through the API. In our example, we want to access monitoring data through the API, so we select the predefined *MonitoringDataRead* role.

    For more information about the available predefined roles, see [Tasks and Permissions](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/556d5575d4b0483e85d4f3251f21d0ec.html "") :arrow_upper_right:.

    > ### Tip:  
    > Make sure you select a role with an application identifier that starts with `it!`.
    > 
    > The *Application Identifier* parameter identifies the SAP BTP application.
    > 
    > Note that remote components can connect to Cloud Integration at different levels, where the level is expressed by different application identifiers.
    > 
    > -   To configure access to Cloud Integration resources as a dialog user \(designing integration flows. for example\) or an API client, you connect the remote system to an application with an *Application Identifier* starting with `it!`.
    > 
    > -   To configure access to Cloud Integration runtime resources \(integration flows\) from a sender, you need to connect the sender to an `it-rt` application.

9.  Choose *Add*.

    Repeat to add more roles to the role collection, if desired.

10. Choose *Save*.

11. Go back to the subaccount and choose *Security* \> *Trust Configuration*.

12. Click the *Default identity provider* link.

13. Enter the email address of the IdP user on whose behalf you want to access Cloud Integration through the API.

14. Click *Show Assignments*.

15. Select *Assign Role Collection*.

    Select the newly defined role collection.

16. Choose *Assign Role Collection*.


You can now call the resource of the OData API from an API client using the credentials of the IdP user.

