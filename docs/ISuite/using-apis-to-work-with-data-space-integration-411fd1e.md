<!-- loio411fd1e522f54d2687e3e80d1978073a -->

# Using APIs to Work With Data Space Integration

Data Space Integration provides APIs for accessing and managing resources, which can be tested on the SAP Business Accelerator Hub. To interact with Data Space Integration using the API, you must create a service instance and service key for inbound authentication.



<a name="loio411fd1e522f54d2687e3e80d1978073a__section_dhh_zll_zzb"/>

## Overview

APIs are provided on the [SAP Business Accelerator Hub](https://api.sap.com/), where you can test the APIs against your existing tenants.

OData APIs are implemented as REST APIs and use the Open Data Protocol as a technical protocol. This means that you can use standard HTTP methods \(for example, the GET method\) to call the API.

You can access the OData APIs available for Data Space Integration at [Data Space Integration \(SAP Business Accelerator Hub\)](https://api.sap.com/package/dataspaceintegration/rest). There you can also find detailed descriptions of each API call.



<a name="loio411fd1e522f54d2687e3e80d1978073a__section_rmq_34l_zzb"/>

## Using APIs vs. User Interface

For some actions in Data Space Integration, you can decide if you either want to use APIs or manually complete the action in the user interface of SAP Integration Suite.

Be aware that the features offered via the API and the user interface can differ. While the **API** adheres to the open-source prerequisites set by the Eclipse Dataspace Connector, the **user interface** of Data Space Integration is developed by SAP and is updated regularly.

Currently, you can only consume assets from other data space participants if you use the API [Data Space Integration \(SAP Business Accelerator Hub\)](https://api.sap.com/package/dataspaceintegration/rest). See [Consuming Data Space Assets](consuming-data-space-assets-5c0cdb8.md).



<a name="loio411fd1e522f54d2687e3e80d1978073a__section_szj_glt_c1c"/>

## Preparation: Retrieving Credentials for Interacting Using APIs

To get access to Data Space Integration using APIs, you must first create a service instance and service key for inbound authentication.



### Prerequisites

-   You've completed the steps described in [Preparatory Steps](preparatory-steps-95366b2.md) where you activate SAP Integration Suite and the Cloud Integration capability.

-   You've completed the steps described in [Activating the Capability](activating-the-capability-b49ad35.md) where you add Data Space Integration to your list of active capabilities of SAP Integration Suite.



### Procedure

1.  Go to the SAP BTP cockpit and navigate to your subaccount that has SAP Integration Suite enabled. From there, go to *Cloud Foundry* \> *Spaces* \> *Your space* \> *Services* \> *Instances*.
2.  Select **Create** to create a new service instance and select `Data Space Integration API Access`. In the **Plan** field, enter `api`, and add an instance name. Then, choose **Next**.
3.  Next, select the applicable role to enforce authorization, `DataspaceConsumer` or `DataspaceProvider`, or both, depending on the needs of the business application that wants to exchange data within the data space. For an overview of the available roles and their authorizations, see [Personas and Roles](60-Security/identity-and-access-management-for-data-space-integration-211c66a.md#loio211c66a2f65e4bf0ad0e93e68cfff984__section_cxz_vsk_pcc).

    Once you've selected the role, select `client_credentials` as the grant type and choose **Next**.

4.  Review the information and select **Create**.
5.  Now, you need to create a service key for your service instance - either with a ClientID/Secret or Certificate.

    For the service instance that was created, select **Create Service Key**. Enter a name for the service key and for the **Key Type** select `ClientID/Secret` or `Certificate`. Leave the rest of the fields as they are. Select **Create**.




### Next Steps

Now that you've created a new service key, you can start interacting with Data Space Integration using the API to register or consume assets. See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).

**Related Information**  


[Consuming Data Space Assets](consuming-data-space-assets-5c0cdb8.md "In Data Space Integration, as a consumer, you want to consume data assets provided by other members of the data space.")

[Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md "Before you can consume an asset of another data space participant, you must discover their catalog and decide on an offer.")

[Consuming S3 and Azure Assets](consuming-s3-and-azure-assets-4afdf5c.md "Learn how to trigger a contract negotiation, agree with a provider on the conditions for using their assets, and transfer assets to your desired location.")

[Consuming HTTP Assets](consuming-http-assets-735300c.md "Learn how to initiate contract negotiations and transfer HTTP assets from a provider's catalog.")

[Triggering Contract Negotiations and Transferring Assets with EDR Management APIs](triggering-contract-negotiations-and-transferring-assets-with-edr-management-apis-eace95e.md "To consume assets, you must agree with the provider on the conditions. This process happens in a contract negotiation, after which you can transfer your assets.")

[Consuming Assets](consuming-assets-f6b27ac.md "You've successfully negotiated the usage of a provider's asset, and you've triggered the transfer process. Now, you can consume the chosen asset.")

