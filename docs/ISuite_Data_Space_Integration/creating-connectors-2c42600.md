<!-- loio2c42600aa4a546158fddc7b04f28e881 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating Connectors

Learn how to create additional connectors, which you can then manage with Data Space Integration.



## Prerequisites

-   You have the role collection `DataspaceConnectorAdmin`.
-   You've completed the steps described in [Initial Setup](initial-setup-b2bdea7.md), except for the final task in which you configure the connector setup.
-   You must have added the service plan `dsi-package` to your subaccount as follows:
    1.  In SAP BTP cockpit, open your subaccount and go to *Entitlements*.
    2.  Choose *Edit*, then *Add Service Plans*.
    3.  Select the service *SAP Integration Suite* and the plan *dsi-package*. To confirm, choose *Add 1 Service Plan*.

-   To create new connectors, you must also have **free quota** available in the `dsi-package` plan in your subaccount. With one quota unit you can create one connector. See also [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/docs/btp/sap-business-technology-platform/configure-entitlements-and-quotas-for-subaccounts).

    Check your available quota as follows:

    1.  Go to your subaccount in SAP BTP cockpit and go to *Entitlements*.
    2.  Go to the entry for the service *SAP Integration Suite*, which includes an entry for the plan `dsi-package`
    3.  Check the quota assignment \(1 quota = 1 connector\):
        -   If there's **quota available** to cover the number of connectors you want to create in Data Space Integration , no action's required.
        -   If it's **too low**, but there's quota available, increase the quota to the desired number by choosing :heavy_plus_sign:.
        -   If it's **too low** and **no quota is available**, please contact your global account administrator.





## Context

With Data Space Integration, you can have more than one connector with which you can collaborate within data spaces with other participants. Only the **connector administrator** has high-level access to all connectors in the connector overview, which is also where they can create new connectors.

As a connector admin, you can set up additional connectors as follows.



## Procedure

1.  Go to *Settings* \> *Data Spaces* and choose *Create Connector*.

2.  Enter a name for the connector. Optionally, you can add a description, for example, describing the use case of the connector. Confirm by choosing *Create*.

    > ### Note:  
    > If the creation fails, you might have depleted your connector quota. In that case, your global administrator must assign more quotas of `dsi-package` to your subaccount. See the prerequisites on this page.




## Next Steps

Now that one or more connectors exist, the **administrator of your SAP BTP subaccount** can create connector-specific roles to give users access to the connectors. See [Creating Role Collections for Connectors](creating-role-collections-for-connectors-119b70a.md).

Once granted one of these roles, a **technical admin** can open the newly created connector and continue the onboarding to a data space as described in [Configuring Connector Setup](configuring-connector-setup-4909d3f.md).

> ### Caution:  
> If you want to host multiple connectors for different companies and use Decentralized Identity Verification for multiple of those companies, ensure the following:
> 
> For each connector that belongs to a separate company, you must create a **new identity** and a **new application** in Decentralized Identity Verification.

