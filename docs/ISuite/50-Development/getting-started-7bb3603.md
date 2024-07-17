<!-- loio7bb3603fc86c4124a303398cf15a6099 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Getting Started

As a Subaccount or Tenant Administrator, you need to perform various steps to use the Graph Configuration API.



<a name="loio7bb3603fc86c4124a303398cf15a6099__section_uwx_gcg_j1c"/>

## Prerequisites

You have:

-   Assigned the role of *Graph\_Key\_User*. You need this role to use the configuration API.

-   Set up your data sources and authorized your user to access all the data sources \(destinations\) in the landscape. Your user needs this authorization to allow Graph to discover the data models.

-   Configured an entitlement for Graph to access the Graph Configuration API. For more information, see [Configure Entitlement for Graph](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_configEntitlement).




<a name="loio7bb3603fc86c4124a303398cf15a6099__section_j34_3cg_j1c"/>

## Create a Graph Service Instance

In the SAP BTP cockpit, go to *Services Instances and Subscriptions* and do the following:

1.  Choose *Create*. The *New Instance or Subscription* wizard opens.

2.  Select the Graph service from the dropdown menu and enter the basic information for your instance.

3.  Select *configuration* for your service plan.

4.  Select *Other* for your runtime environment.

    > ### Note:  
    > Other runtime environments are also supported, but not required

5.  Enter a name for your instance, and choose *Create*.




<a name="loio7bb3603fc86c4124a303398cf15a6099__section_j2m_rgd_k1c"/>

## Create and Download a Service Binding

The Graph key user must have a service binding to obtain the access credentials to consume it.

1.  In the SAP BTP cockpit, go to *Services Instances and Subscriptions* and choose <span class="SAP-icons-V5"></span>. Select *Create Service Binding*, enter any name, and choose *Create*.

2.  Choose <span class="SAP-icons-V5"></span> to download a text file of the service binding.

    For more information, see [Creating Service Bindings in Other Environments](https://help.sap.com/docs/service-manager/sap-service-manager/creating-service-bindings-in-other-environments?version=Cloud).


