<!-- loio2d113a1343cd4e34b33a8460344361a1 -->

# Enabling Users

You need users in the system for a scenario to work. Graph does not manage user identities and it cannot directly authenticate clients. Instead, it relies on the XSUAA, SAP Authorization and Trust Management Service to do that. By setting a trust relationship to XSUAA, Graph accepts the identities verified by XSUAA and passed to it in the form of bearer tokens. It supports token-based authentication.

There are two ways to define users. For the purpose of bootstraps, demos, and PoCs, an administrator can simply add users, one-by-one, to the SAP BTP subaccount \(for example, via the SAP BTP cockpit\). But while XSUAA can manage such user collections, most organizations prefer to use their own user base and Identity Provider \(IdP\).

SAP BTP supports identity federation, linking and reusing digital identities of a user base across loosely coupled systems. The federation is implemented using [SAP Cloud Identity Services - Identity Authentication \(IAS\)](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/19f3eca47db643b6aad448b5dc1075ad.html) in the role of federating proxy. Setting up the trust between the SAP BTP subaccount \(XSUAA\) and IAS is described in [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html?version=Cloud).

> ### Note:  
> The added IdP must be enabled for interactive user login, to ensure that XSUAA redirects to the IAS login form when authenticating users. Shadow user creation must also be enabled to create copies of users from IAS to XSUAA.

After setting trust, XSUAA can authenticate users from the given IdP. Since Graph has a trust relationship to XSUAA, it will be able to validate the tokens that it issued.

