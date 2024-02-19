<!-- loioca75e12fc5904d96a038aef6c00db5fc -->

# HTTP Calls and URI Components



An HTTP call is composed of a **service root URI**, **resource path**, and **query options**.

To find the **resource path** and the supported **query options**, go to SAP Business Accelerator Hub and select the API. For example, to find the resource paths, the supported operations and query options for message processing logs, check out the [Message Processing Logs](https://api.sap.com/api/MessageProcessingLogs/resource) page on SAP Business Accelerator Hub.



To get the **service root URI**, perform the following steps:

Open SAP BTP cockpit, go to the subaccount and choose *Instances and Subscriptions*. View the details of the service key that you have created when setting up inbound authentication for API access, and find the `url` parameter \(see [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md)\). Throughout this documentation, we refer to this part of the address also as **host address**.

> ### Note:  
> If you have set up inbound API access with basic authentication of an IdP user \(according to [Basic Authentication of an IdP User for API Clients](../40-RemoteSystems/basic-authentication-of-an-idp-user-for-api-clients-57f104d.md)\), no service key is in place. In this case, create a service key \(with plan api as described at [Creating Service Instance and Service Key for Inbound Authentication](../40-RemoteSystems/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md)\), get the url parameter and delete the service key after you have retrieved the service root URI.

The service root URI then is derived by appending `/api/v1`.

The service root URI is then: `<url parameter from service key>/api/v1`.

For example, to get all message processing logs with status *Completed*, use the following call:

`https://12345abc.it-xyz789.cfapps.us10-001.hana.ondemand.com/api/v1/MessageProcessingLogs?$filter=Status eq 'COMPLETED'`

In the example, these are the URI components:

-   Service root URI:

    `https://12345abc.it-xyz789.cfapps.us10-001.hana.ondemand.com/api/v1` \(where `https://12345abc.it-xyz789.cfapps.us10-001.hana.ondemand.com` is the url parameter of the service key\)

-   Resource path:

    `MessageProcessingLogs`

-   Query option:

    `$filter=Status eq 'COMPLETED'`




For more information about the service root URI, resource path, and query options, see [URI Conventions \(OData Version 2.0\)](http://www.odata.org/documentation/odata-version-2-0/uri-conventions).

> ### Caution:  
> The browser translates space characters to `%20`. If you paste a URL from this documentation to the browser, the OData call therefore works. The string `%20` is left out of the example URLs to make them easier to read.

