<!-- loio1e7489f7226545e9a7936b99d1de298a -->

# Fix Keystore Synchronization Issues

Fix keystore issues by synchronizing the nodes of your Kubernetes cluster with Coordinated Universal Time \(UTC\).



<a name="loio1e7489f7226545e9a7936b99d1de298a__section_dt3_btl_zbc"/>

## Symptom/Issue

-   The status of the keystore associated with your Edge Integration Cell runtime is *Stored* instead of the expected status, *Deployed*. The status *Stored* means that the keystore of your Edge Integration Cell is deployed but not yet synchronized with the associated runtime.

    > ### Remember:  
    > You can manage your keystores in the *Monitor* section of the SAP Integration Suite. Search for the *Manage Keystore* tile under *Manage Security*.

-   You find the error “`JWT verification failed`” in the logs of the `esac` pod. The following snippet shows the stack trace of the error in the downloaded diagnostic data from the Edge Node:

    > ### Output Code:  
    > ```
    > com.sap.cp.security.credstore.client.CredentialStoreErrorResponseException: Unexpected status code 400 while retrieving access token: POST https://credstoreauth.cfapps.us10.hana.ondemand.com/api/v1/token HTTP/1.1 {"errorCode":"invalid_grant","errorDescription":"JWT verification failed","httpStatus":"BAD_REQUEST"}
    >         at com.sap.cp.security.credstore.client.OAuthTokenRetriever.retryTokenRequest(OAuthTokenRetriever.java:154)
    >         at com.sap.cp.security.credstore.client.OAuthTokenRetriever.parseToken(OAuthTokenRetriever.java:91)
    >         at com.sap.cp.security.credstore.client.OAuthTokenRetriever.retrieveNewOAuthToken(OAuthTokenRetriever.java:171)
    >         at com.sap.cp.security.credstore.client.OAuthTokenRetrieverNamespace.obtainNewToken(OAuthTokenRetrieverNamespace.java:145)
    >         at com.sap.cp.security.credstore.client.OAuthTokenRetrieverNamespace.computeCachedToken(OAuthTokenRetrieverNamespace.java:138)
    > 
    > 
    > ```

    You can access the stack trace by following this navigation path in the diagnostics zip file:`edge-icell/pod-logs/edge-icell/esac-<guid>/esac`.

    For more information, see [Downloading Diagnostic Data from an Edge Node](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/3ac0188c92124823a2ce921f40e317af.html).




<a name="loio1e7489f7226545e9a7936b99d1de298a__section_ljx_f5l_zbc"/>

## Solution

Contact the administrator of the Kubernetes cluster and ask them to synchronize the time of the nodes of the Kubernetes cluster with Coordinated Universal Time \(UTC\). For more information, see [Time synchronization in Kubernetes](https://kubeops.net/blog/time-synchronization-in-kubernetes).

