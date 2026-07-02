<!-- loio3a810c8c87814718b654bd4b59929522 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Changing the Landscape of Your Connector

Learn how to change the landscape of your connector in Data Space Integration.



## Prerequisites

Your user has the role collections `PI_Administrator` and `DataspaceTechnicalAdmin`.



## Context

You want to update your connector details because you changed the landscape.



## Procedure

1.  In your old landscape portal \(for example, Catena-X or Cofinity-X\), delete the old connector as follows:

    1.  Open the landscape portal and go to *Technical Setup* \> *Connector Registration*.

    2.  In the list of owned connectors, find the connector that you want to delete and choose :wastebasket:.

        ![](images/DSI-deprovisioning-delete-connector_664e52c.png)

    3.  In the confirmation dialog, choose *Deactivate*.


2.  Additionally, we recommend that you delete the security material that you created in SAP Integration Suite to activate Data Space Integration. If you're using the security material anywhere else, first check with their consumers to decide whether the items can be deleted.

    Don't delete the Cloud Integration service keys, the custom role, and the deployed integration flows. You can reuse them.

    1.  In SAP Integration Suite, go to *Monitor* \> *Integrations and APIs*.

    2.  Open the *Security Material* tile.

    3.  For all entries that contain "SAP\_DataspaceIntegration" within their name, choose :wastebasket:.


3.  You can now go to *Settings* \> *Data Spaces* and choose *Edit*. Modify the landscape and other details of your new connector, then save your changes.

    You can leave the other two tabs, *Prepare Connector to Cloud Integration* and *Onboard the Data Plane*, as they are.


