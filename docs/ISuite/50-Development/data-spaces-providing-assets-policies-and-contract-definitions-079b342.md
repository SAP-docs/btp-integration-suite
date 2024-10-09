<!-- loio079b342a395f465b973b9b7b132219b7 -->

# Data Spaces - Providing Assets, Policies, and Contract Definitions

In Data Space Integration, as a provider, you want to create assets and policies, and bundle them into contract definitions to facilitate data exchange between different members of your network.



> ### Note:  
> This section focuses on working with Data Space Integration as a **provider**. If you're a consumer who wants to work with another data space participants' assets, see [Consuming Data Space Assets](../consuming-data-space-assets-5c0cdb8.md).



<a name="loio079b342a395f465b973b9b7b132219b7__section_cmc_tt1_mzb"/>

## Prerequisites

To work with assets, policies, and contract agreements, your user requires the `DataspaceProvider` role collection. See [Configuring User Access](../configuring-user-access-6ae0ff7.md) and [Personas and Roles](../60-Security/identity-and-access-management-for-data-space-integration-211c66a.md#loio211c66a2f65e4bf0ad0e93e68cfff984__section_cxz_vsk_pcc).



<a name="loio079b342a395f465b973b9b7b132219b7__section_kkd_ljq_gyb"/>

## Overview

In Data Space Integration, providers and consumers of assets can define data exchange via contract agreements in a sovereign and secure way. See [Concepts in Data Space Integration](../concepts-in-data-space-integration-fcf96b2.md).

![The diagram shows how the participants of a data space interact with each other. First, the provider creates both assets and policies, which come together to form a contract definition. Based on the contract definition, the provider creates a contract offer. At this point, provider and consumer together begin the contract negotiation based on the contract offer. This process of negotiating and creating offers can take multiple iterations. After successful negotiations between provider and consumer, a contract agreement is reached.](../images/Dataspace_Interaction_Process_a605456.jpg)



<a name="loio079b342a395f465b973b9b7b132219b7__section_dbj_tjq_gyb"/>

## Provide Data Space Assets

To facilitate data exchange, as a provider, you need to perform the following steps:

1.  Define assets that you would like to offer. Multiple assets can be bundled together.

    See [Creating Assets](creating-assets-5e051be.md).

2.  Define policies regulating the way users interact with your assets.

    See [Creating Policies](creating-policies-91458cf.md).

3.  Bundle assets and policies and offer them in contract definitions to other members of the data space for consumption.

    See [Creating Contract Definitions](creating-contract-definitions-7746d65.md).


After you've completed this setup, your assets are ready to be consumed.

