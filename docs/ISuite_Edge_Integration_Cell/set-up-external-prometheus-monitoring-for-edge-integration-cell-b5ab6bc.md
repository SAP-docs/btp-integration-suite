<!-- loiob5ab6bc7e4bc445684c1b2cce666072c -->

# Set Up External Prometheus Monitoring for Edge Integration Cell

Configure an external Prometheus instance to scrape metrics from Edge Integration Cell. Choose from three deployment scenarios tailored to your specific TLS encryption and built-in monitoring requirements.



<a name="loiob5ab6bc7e4bc445684c1b2cce666072c__prereq_prometheus_eic"/>

## Prerequisites

Edge Integration Cell automatically merges its metrics with Istio metrics. Consequently, Istio Metrics Merging must be enabled on your cluster, making the data available in plain text. For configuration details, see [Istio Prometheus Integration: Metrics Merging](https://istio.io/latest/docs/ops/integrations/prometheus/#option-1-metrics-merging).



## Context

By default, Edge Integration Cell relies on the built-in logging and monitoring capabilities of Edge Lifecycle Management. To use an external Prometheus instance to scrape these metrics instead, implement one of the configuration options below. For more information, see [Monitoring and Logging](https://help.sap.com/docs/edge-lifecycle-management/documentation/monitoring-and-logging).



## Procedure

1.  External Prometheus Without Built-in Monitoring and Without TLS

    Use this scenario to scrape metrics using an external Prometheus instance without the built-in Edge Lifecycle Management monitoring capabilities and without TLS encryption.

    1.  Create a Network Policy.

        Apply a network policy to allow ingress traffic from Prometheus to the `edge-icell` namespace. Replace `<prometheus-namespace>` with the actual namespace where your Prometheus instance is running.

        > ### Sample Code:  
        > ```
        > apiVersion: networking.k8s.io/v1
        > kind: NetworkPolicy
        > metadata:
        >   name: allow-monitoring-namespaces
        >   namespace: edge-icell
        > spec:
        >   podSelector: {}
        >   ingress:
        >     - from:
        >         - namespaceSelector:
        >             matchLabels:
        >               kubernetes.io/metadata.name: <prometheus-namespace>
        >   policyTypes:
        >     - Ingress
        > ```


2.  With Built-in Edge Lifecycle Management Monitoring and TLS

    Use this scenario if you retain the built-in Edge Lifecycle Management logging and monitoring but require TLS encryption for the metrics.

    1.  Disable Istio Metrics Merging.

        Manually edit the `ssb-operator-default-config` ConfigMap in the `edge-icell-services` namespace and set `PROMETHEUS_MERGE=false`. You can execute this directly via:

        > ### Sample Code:  
        > ```
        > kubectl edit configmap ssb-operator-default-config -n edge-icell-services
        > ```

    2.  Propagate the Configuration.

        In Edge Lifecycle Management, trigger the `Modify Configuration` action for the Edge Integration Cell Services solution. You do not need to alter any values in the configuration UI; running the action automatically propagates the new settings to the Edge Integration Cell.


3.  External Prometheus Without Built-in Monitoring and With TLS

    Use this scenario to scrape metrics using an external Prometheus instance without the built-in Edge Lifecycle Management capabilities, while strictly requiring TLS encryption.

    1.  Set Up Istio Certificates.

        Ensure your certificates are placed in the fixed file paths required by the Edge Integration Cell service monitoring configuration:

        -   CA file: `/etc/prom-certs/root-cert.pem`

        -   Certificate file: `/etc/prom-certs/cert-chain.pem`

        -   Key file: `/etc/prom-certs/key.pem`


    2.  Disable Istio Metrics Merging.

        Manually edit the `ssb-operator-default-config` ConfigMap in the `edge-icell-services` namespace and set `PROMETHEUS_MERGE=false`:

        > ### Sample Code:  
        > ```
        > kubectl edit configmap ssb-operator-default-config -n edge-icell-services
        > ```

    3.  Propagate the Configuration.

        In Edge Lifecycle Management, run the `Modify Configuration` action for the Edge Integration Cell Services solution to push the updated settings to the Edge Integration Cell.

    4.  Create a Network Policy.

        Apply a network policy to allow traffic from your Prometheus namespace to the `edge-icell` namespace. Replace `<prometheus-namespace>` with your actual Prometheus namespace.

        > ### Sample Code:  
        > ```
        > 
        > apiVersion: networking.k8s.io/v1
        > kind: NetworkPolicy
        > metadata:
        >   name: allow-monitoring-namespaces
        >   namespace: edge-icell
        > spec:
        >   podSelector: {}
        >   ingress:
        >     - from:
        >         - namespaceSelector:
        >             matchLabels:
        >               kubernetes.io/metadata.name: <prometheus-namespace>
        >   policyTypes:
        >     - Ingress
        > ```

    5.  Create Authorization Policies for Components.

        Configure an `AuthorizationPolicy` for each component exposing a metrics endpoint to grant scraping permissions to Prometheus. Replace `<prometheus-namespace>` with your Prometheus namespace, `<component>` with the component name, and `<metrics-endpoint-path>` with the respective path from the reference table below.

        > ### Sample Code:  
        > ```
        > apiVersion: security.istio.io/v1beta1
        > kind: AuthorizationPolicy
        > metadata:
        >   name: <component>-monitoring-auth-policy
        >   namespace: edge-icell
        > spec:
        >   selector:
        >     matchLabels:
        >       app: <component>
        >       app.kubernetes.io/name: <component>
        >   action: ALLOW
        >   rules:
        >     - from:
        >         - source:
        >             namespaces:
        >               - <prometheus-namespace>
        >       to:
        >         - operation:
        >             methods:
        >               - GET
        >             paths:
        >               - <metrics-endpoint-path>
        > ```

        **Component Metrics Endpoints**


        <table>
        <tr>
        <th valign="top">

        Component Name
        
        </th>
        <th valign="top">

        Metrics Endpoint Path
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        auditlog-agent
        
        </td>
        <td valign="top">
        
        /audit-log/oauth2/actuator/prometheus
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        edc
        
        </td>
        <td valign="top">
        
        /metrics
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        edge-event-controller
        
        </td>
        <td valign="top">
        
        /metrics
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        esac
        
        </td>
        <td valign="top">
        
        /actuator/prometheus
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        mdc
        
        </td>
        <td valign="top">
        
        /actuator/prometheus
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        policyengine
        
        </td>
        <td valign="top">
        
        /metrics
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        worker
        
        </td>
        <td valign="top">
        
        /metrics
        
        </td>
        </tr>
        </table>
        


