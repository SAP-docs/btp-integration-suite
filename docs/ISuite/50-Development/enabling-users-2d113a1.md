<!-- loio2d113a1343cd4e34b33a8460344361a1 -->

# Enabling Users

You need users in the system for a scenario to work.

Graph does not manage user identities and it cannot directly authenticate clients. Instead, it relies on the SAP Authorization and Trust Management service to do that. By setting a trust relationship to SAP Authorization and Trust Management, Graph accepts the identities verified by SAP Authorization and Trust Management and passed to it in the form of bearer tokens. It supports token-based authentication.

There are two ways to define users. For the purpose of bootstraps, demos, and PoCs, an administrator can simply add users, one-by-one, to the SAP BTP subaccount \(for example, via the SAP BTP cockpit\). But while the SAP Authorization and Trust Management service can manage such user collections, most organizations prefer to use their own user base and Identity Provider \(IdP\).

SAP BTP supports identity federation, linking and reusing digital identities of a user base across loosely coupled systems. The federation is implemented using [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/19f3eca47db643b6aad448b5dc1075ad.html) in the role of federating proxy. Setting up the trust between the SAP BTP subaccount and corporate identity providers are described in [Establish Trust and Federation Between SAP Authorization and Trust Management Service and SAP Cloud Identity Authentication](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html?version=Cloud).

> ### Note:  
> The added IdP must be enabled for interactive user login, to ensure that SAP Authorization and Trust Management redirects to the corporate identity provider login form when authenticating users. Shadow user creation must also be enabled to create copies of users from IAS to SAP Authorization and Trust Management.

After setting trust, SAP Authorization and Trust Management Service can authenticate users from the given IdP. Since Graph has a trust relationship to SAP Authorization and Trust Management Service, it will be able to validate the tokens that it issued.



<a name="loio2d113a1343cd4e34b33a8460344361a1__section_h4z_yfy_pcc"/>

## Enabling Key Users

The creation and activation of business data graphs is managed by a user with a special role, called the Graph key user.

The key user uses Graph on the Integration Suite home page to configure a business data graph. After activating Graph as a capability of API Management within SAP Integration Suite, the role of `Graph_Key_User` must be assigned to a role collection in the SAP BTP cockpit.



<a name="loio2d113a1343cd4e34b33a8460344361a1__section_oqc_rhy_pcc"/>

## Enabling Guest Users

If someone needs to review and understand how a business data graph is configured, but doesn't need permissions to make changes, then an administrator can assign them the role of `Graph_Guest`. A Graph guest is given read-only access to Graph and the Graph Configuration API.

**Related Information**  


[Initial Setup](initial-setup-12ad448.md "As a Subaccount or Tenant Administrator, you need to add Graph as a capability of API Management within SAP Integration Suite.")

[Create a Business Data Graph in Integration Suite](create-a-business-data-graph-in-integration-suite-42daf3b.md "As a Graph Key User, you can create a new business data graph. You can also use an existing configuration file to create a business data graph.")

[Define Users](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_DefineUsers)

