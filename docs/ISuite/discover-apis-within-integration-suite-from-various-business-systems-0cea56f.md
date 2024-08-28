<!-- loio0cea56f28514435ab3d61c2416ca9170 -->

# Discover APIs within Integration Suite from Various Business Systems

As a content administrator, you can make your APIs available on the API business hub enterprise catalog by discovering and publishing them from various business systems.



<a name="loio0cea56f28514435ab3d61c2416ca9170__section_ccw_5tx_gbc"/>

## How to discover business systems in API business hub enterprise?

To discover the APIs from various business systems in the API business hub enterprise, you first need to ask the *Global Account Administrator* to register these systems in the SAP BTP Cockpit.

The Global Account Administrator organizes SAP systems into groups so that they can be extended in a business scenario at one go. To accomplish this, the administrator creates a formation containing one or more different systems assigned to a common subaccount. For the Integration Suite to recognize these systems, they need to be part of the group. See [Enabling System Landscape in SAP BTP Cockpit for SAP Integration Suite](40-RemoteSystems/enabling-system-landscape-in-sap-btp-cockpit-for-sap-integration-suite-88bac3b.md) topic for step-by-step instructions on how to register and connect the SAP Integration Suite business system with your global account.



<a name="loio0cea56f28514435ab3d61c2416ca9170__section_kcb_k5x_gbc"/>

## How do you discover and publish products from business systems?

You need to have the*AuthGroup.Content.Admin* role collection assigned to you. After the business systems are successfully registered and linked, you, as a content administrator, can perform the following actions:

-   Navigate to the *Business Systems* tab under *Manage Content* to view the list of systems added to your global account.

-   Fetch the APIs from the respective business systems by selecting the system and accessing the APIs within each system.

    > ### Note:  
    > The APIs are located within the *Consumption Bundles*. A consumption bundle groups together a set of related APIs that can be accessed with the same credentials. You can select the consumption bundles to view the APIs contained within them. Furthermore, you can select individual APIs to access their details and documentation.

-   To create products, start by selecting a system from the *Business Systems* page. Then, choose the consumption bundle\(s\) that contain the APIs that you want to publish to the catalog. These consumption bundles can be published as products to make the APIs available in the catalog. You can easily view and manage the products you have created from the *Products* tab. For more information, see [Create Products from Business Systems](create-products-from-business-systems-08aff91.md).


