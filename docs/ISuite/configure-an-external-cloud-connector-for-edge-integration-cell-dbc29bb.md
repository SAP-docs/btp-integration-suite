<!-- loiodbc29bbfa44746d69290874a458a3bef -->

# Configure an External Cloud Connector for Edge Integration Cell

If you use an external Cloud Connector, additional configuration is required before you deploy the Edge Integration Cell solution.



<a name="loiodbc29bbfa44746d69290874a458a3bef__prereq_ext_cc_eic"/>

## Prerequisites

You are using an external Cloud Connector.



## Context

This configuration includes solution properties, access control for monitoring APIs, system mapping, resource definitions, and trust configuration.

> ### Note:  
> Use this procedure only with an external Cloud Connector. The external Cloud Connector is operated outside Edge Lifecycle Management.



## Procedure

1.  During *Deploy the Edge Integration Cell Solution* procedure, set the following solution properties:

    -   `API Virtual Host`

    -   `API Virtual Host Key Alias`

    -   `Cloud Connector Virtual Host`


2.  In the External Cloud Connector Administration UI, define access control for the monitoring APIs as described in[Configure Access Control \(HTTP\)](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-http?version=Cloud).

3.  Add a system mapping with the following values:

    -   **Back-end Type:** Other SAP System

    -   **Protocol:** HTTPS

    -   **Internal Host:** `<API Virtual Host>`

    -   **Internal Port:** `443`

    -   **Virtual Host:** `<Cloud Connector Virtual Host - hostname>`

    -   **Virtual Port:** `<Cloud Connector Virtual Host - port>`

    -   **Allow Principal Propagation:** `false`

    -   **System Certificate for Logon:** `false`

    -   **Host in Request Header:** Use Internal Host


4.  Add the following resources:

    -   `/Operations`

        -   **Active:** `true`

        -   **Upgrade Allowed:** `false`

        -   **Access Policy:** Path and All Sub-Paths


    -   `/api`

        -   **Active:** `true`

        -   **Upgrade Allowed:** `false`

        -   **Access Policy:** Path and All Sub-Paths



5.  Add the CA certificate for the `API Virtual Host` as described in [Configure Trust](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-http?version=Cloud).




<a name="loiodbc29bbfa44746d69290874a458a3bef__result_ext_cc_eic"/>

## Results

After you complete the configuration:

-   The external Cloud Connector is configured for use with Edge Integration Cell.

-   The required access settings for the monitoring APIs are in place.

-   You can now proceed with deploying the Edge Integration Cell solution.


