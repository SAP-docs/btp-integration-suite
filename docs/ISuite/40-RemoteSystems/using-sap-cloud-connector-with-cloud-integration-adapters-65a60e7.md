<!-- loio65a60e750eca49328fef93c0723ad4b8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using SAP Cloud Connector with Cloud Integration Adapters

You can use the SAP Cloud Connector \(SCC\) with Cloud Integration adapters to communicate with SAP on premise systems. You have to install cloud connector on the on premise system/s that you want to communicate with, and configure it. This is a one-time activity after which you can use cloud connector with Cloud Integration adapters.

Perform the following steps to use cloud connector with Cloud Integration adapters.

1.  Install SAP Cloud Connector on your on premise system. For more information, see [Installing the Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html).

2.  For SAP BTP, **Cloud Foundry** environment, you need to create a role collection for your subaccout. Follow the mentioned steps next:
    1.  From your subaccount, navigate to *Security* \> *Role Collections*.

    2.  Choose Add role collection:heavy_plus_sign: and enter a value for *Name*\(Example: CloudConnector\) and *Description* and choose *Create*.
    3.  Open the newly created role collection and choose *Edit*.
    4.  Under the *Roles* section, choose Add role collection:heavy_plus_sign: and assign the role *Cloud Connector Administrator* from the drop-down list.
    5.  Under the *Users* section, choose Add role collection:heavy_plus_sign: and enter the *ID* and *E-Mail* of the user to whom you need to provide access to connect to the cloud connector. Let the value of the *Identity Provider* be *ldap*.
    6.  Choose *Save*.

3.  Set up mutual authentication between the cloud connector and a backend system. For more information, see [Initial Configuration](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/db9170a7d97610148537d5a84bf79ba2.html) and [Initial Configuration \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/3f974eae3cba4dafa274ec59f69daba6.html).

4.  Enable the web application to connect to access backend system on the intranet. For more information, see [Configuring Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html).


You can now connect to on premise systems using Cloud Integration adapters by selecting *on-premise* value in *Proxy Type* field dropdown list.

> ### Remember:  
> Here are some important considerations while using SAP Cloud Connector with Cloud Integration adapters:
> 
> -   Ensure that the receiver URL starts with `http://` while configuring the integration flow.
> -   Always use *Basic Authentication* as the *<Authentication Type\>*.
> -   Ensure that you deploy the credentials that enables access to the backend system that you are trying to connect to.
> -   Ensure that you use the correct *Location ID* of the cloud connector that you want to establish a connection to. You can find this in the configuration of the cloud connector in the target system. For more information, you can also see this blog: [Connecting multiple Cloud Connectors to an account in SAP BTP](https://blogs.sap.com/2017/02/06/connecting-multiple-cloud-connectors-to-an-account-in-hana-cloud-platform/)

