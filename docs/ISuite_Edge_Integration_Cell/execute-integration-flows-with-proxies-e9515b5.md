<!-- loioe9515b5b42e641c4839104ccb860b530 -->

# Execute Integration Flows with Proxies

Execute integration flows that include manual proxy configuration.



## Context

Some integration flow adapters allow the configuration of a *Proxy Type* to connect to the target system. When using *Proxy Type*: `Manual Proxy`, a dedicated proxy can be configured that is used within your environment to direct traffic through it. Edge Integration Cell uses Istio as a traffic management framework. Therefore, external proxies have to be configured specifically for Istio to route traffic accordingly.



## Procedure

1.  Open an editor.

2.  Paste the following template:

    > ### Sample Code:  
    > ```
    > apiVersion: networking.istio.io/v1beta1
    > kind: ServiceEntry
    > metadata:
    > name: <proxy-name>
    > namespace: edge-icell
    > spec:
    > hosts:
    > - <proxy-host>
    > ports:
    > - number: <proxy-port>
    > name: tcp
    > protocol: TCP
    > location: MESH_EXTERNAL
    > resolution: DNS
    > ```

3.  Replace `<proxy-name>`, `<proxy-host>`, and `<proxy-port>` and save the file as `proxy-service.yaml`.

4.  Create an Istio service entry using : `kubectl apply -f proxy-service.yaml`.




<a name="loioe9515b5b42e641c4839104ccb860b530__result_ccr_nhh_yyb"/>

## Results

You've created an Istio service entry to direct traffic to an external proxy. For additional background information, see [https://istio.io/latest/docs/tasks/traffic-management/egress/http-proxy/](https://istio.io/latest/docs/tasks/traffic-management/egress/http-proxy/).

