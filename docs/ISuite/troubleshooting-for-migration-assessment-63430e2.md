<!-- loio63430e2bee434c17858331f109777a3a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Troubleshooting for Migration Assessment

Find troubleshooting information for Migration Assessment errors.



<a name="loio63430e2bee434c17858331f109777a3a__section_dzn_kzt_jcc"/>

## Overview

This section covers the following errors on Migration Assessment:

-   Connection test errors:

    > ### Remember:  
    > Connection tests verify whether the main resources needed for the SAP Process Orchestration extraction are reachable. You can get a connection test error even if previous Cloud Connector and destination connection tests were successful, as those don't check for resource accessibility.

    -   [503 Service Unavailable](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_twg_wvt_jcc)
    -   [403 Forbidden](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_ib4_p15_jcc)
    -   [401 Unauthorized](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_zrl_fc5_jcc)
    -   [404 Not Found](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_knt_fry_ffc)

-   [ICO List Empty](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_fby_gqy_ffc)
-   [Technical Error with Unique ID](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_vl2_jc5_jcc)
-   [Network Issue Between Cloud Connector and SAP Process Orchestration](troubleshooting-for-migration-assessment-63430e2.md#loio63430e2bee434c17858331f109777a3a__section_vn4_lc5_jcc)

For more resources, check the [SAP Integration Suite Community](https://pages.community.sap.com/topics/integration-suite), or use the built-in support on Migration Assessment by selecting <span class="SAP-icons-V5"></span> Get Support from the top toolbar.

Use the following component to allow the correct ticket routing: `BC-CP-IS-PIMAS` and provide as much of the following information as possible to improve the analysis of your support ticket:

-   Screenshot of the system configuration in *Migration Assessment*.
-   Screenshots of your Cloud Connector configurations.
-   Screenshot of test connection output dialog.
-   Screenshots of the extraction error logs or Process Orchestration system logs you got while following the troubleshooting steps.
-   If the API calls failed while following the troubleshooting steps, provide screenshots of the API call response of the HEAD operation.
-   If destinations test connection fails, provide screenshots of the destinations configurations with names `PO_<system name>_DIR` and `PO_<system name>_ESR`, where `<system name>` is the name you provided during the system configuration in *Migration Assessment*.



<a name="loio63430e2bee434c17858331f109777a3a__section_twg_wvt_jcc"/>

## 503 Service Unavailable

503 Service Unavailable error means that BTP is not able to reach the SAP Process Orchestration system. Possible reasons for this error include the following:

-   Wrong host or port. Make sure that you maintained virtual host and port in system configuration.

-   If two cloud connectors are configured for the same subaccount, it's mandatory to maintain the *Location Id* field in the system configuration.


Perform the following steps to solve this error:

1.  Make sure that Cloud Connector is configured for the same SAP BTP subaccount on which you're using Migration Assessment.

2.  Check that all paths and sub-paths are exposed as described in [Add an SAP Process Orchestration System](add-an-sap-process-orchestration-system-5f76723.md).
3.  Creating a system in Migration Assessment results in the creation of two destinations on your SAP BTP subaccount. Manually check the destination connection on the subaccount. The following are the destination names:

    -   Integration Directory Destination: `PO_<system name>_DIR`

    -   ESR Destination: `PO_<system name>_ESR`

    > ### Note:  
    > For more information on destinations, see [Configuring Connectivity to an SAP Process Orchestration System](50-Development/IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md)

    If the destination connection works, move to the next step. Otherwise, raise a support ticket with screenshots of the error and destination configurations.

4.  Try to perform the following two API calls with *HEAD* operation in Postman or SOAP UI using basic authentication with the same user you used to configure the system in Migration Assessment:

    -   ```
<system_address>/rep/read/ext
```

    -   ```
<system_address>/IntegratedConfiguration750InService/IntegratedConfiguration750InImplBean
```


    You may move to the next step if the responses of the previous two API calls are empty and the response code is 200. Otherwise, raise a support ticket with screenshots of the error response of the call.

5.  To ensure proper connectivity for the Migration Assessment app to access the SAP Process Orchestration system through Cloud Connector, configure the firewall rules to allow outbound traffic from the Cloud Connector server to the BTP subaccount endpoint. For more details, see [Cloud Connector Installation Network Prerequisites](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/prerequisites#loioe23f776e4d594fdbaeeb1196d47bbcc0__cf).

6.  Check if Cloud connector and JVM versions are outdated as per the SAP Note [3302250](https://me.sap.com/notes/3302250).

    If they're outdated, upgrade to the latest version and then retry.




<a name="loio63430e2bee434c17858331f109777a3a__section_ib4_p15_jcc"/>

## 403 Forbidden



### Possible reasons for the error

-   User roles are missing for the configured user.

-   Your user is inactive, or you must change the initial user password. Check the Integration Builder and Enterprise Service Repository.
-   Firewall/Web Dispatcher is blocking the request with 403.



### Perform cross-check

To cross-check, try to perform the following two API calls with *HEAD* operation in Postman or SOAP UI using the same user you used to configure the system:

-   ```
<system_address>/rep/read/ext 
```

-   ```
<system_address>/IntegratedConfiguration750InService/IntegratedConfiguration750InImplBean 
```




<a name="loio63430e2bee434c17858331f109777a3a__section_zrl_fc5_jcc"/>

## 401 Unauthorized

Reasons for the error:

-   User and password don't exist on the SAP Process Orchestration system.

-   Firewall is blocking the request with 401.



<a name="loio63430e2bee434c17858331f109777a3a__section_knt_fry_ffc"/>

## 404 Not Found

A possible reason for this error could be a wrong SAP Process Orchestration system address configuration.

Make sure you maintain `<host_url>:<port>` in the system configuration address field.



<a name="loio63430e2bee434c17858331f109777a3a__section_fby_gqy_ffc"/>

## ICO List Empty

If you get this error in your extraction logs, perform the following steps:

1.  Check the Cloud Connector logs to identify connectivity issues by following the instructions on the SAP note [2452568](https://me.sap.com/notes/2452568).
2.  If the Cloud Connector logs are unclear, check the SAP Process Orchestration system logs:
    -   Log in to your SAP Process Orchestration system.
    -   Navigate to NetWeaver Administrator.
    -   Go to *Troubleshooting* \> *Logs and Traces* \> *Log Viewer*.
    -   Select *Log Viewer* from the monitoring section and look for exceptions related to the POST calls to `/IntegratedConfiguration750InService/IntegratedConfiguration750InImplBean`.

3.  If the issue persists after checking the logs, raise a support ticket with screenshots of the logs from Cloud Connector and/or SAP Process Orchestration.



<a name="loio63430e2bee434c17858331f109777a3a__section_vl2_jc5_jcc"/>

## Technical Error with Unique ID

If you get a technical error with a unique ID, raise a support incident with the unique ID.



<a name="loio63430e2bee434c17858331f109777a3a__section_vn4_lc5_jcc"/>

## Network Issue Between Cloud Connector and SAP Process Orchestration

When you test the system connection from Migration Assessment, you can see calls to the SAP Process Orchestration system with the relative URLs `IntegratedConfiguration750InService/IntegratedConfiguration750InImplBean` and `rep/read/ext` in your Cloud Connector monitor \(*Most Recent Requests*\). There you can see request details, which means that the request reaches to Cloud Connector. Still, there could be something wrong from the Cloud Connector to SAP Process Orchestration connectivity. You can use the following CURL commands from your Cloud Connector machine to test connectivity to the SAP Process Orchestration system:

-   ```
curl –I --insecure --user user:pwd <system_address>/rep/read/ext
```

-   ```
curl –I --insecure --user user:pwd <system_address>/IntegratedConfiguration750InService/IntegratedConfiguration750InImplBean 
```


If the response of the command is not 200, look into the SAP Process Orchestration system logs for the configured user and check if the request is reaching the SAP Process Orchestration system.

