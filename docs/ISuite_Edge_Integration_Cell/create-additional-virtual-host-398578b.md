<!-- loio398578b3c4ec439092ae1bfb0516148a -->

# Create Additional Virtual Host

Create a virtual host in addition to the existing default virtual host.



## Context

You might need to expose an additional hostname \(alias\) for ingress handling that differs from the default virtual host, or you want to execute integration flows that include manual proxy configurations. To enable this, you can create a dedicated Istio configuration.

> ### Note:  
> Istio resource objects must be compatible with the underlying Istio release version.



## Procedure

1.  Create a file named `gateway.yaml` in your editor and paste the following template:

    > ### Sample Code:  
    > ```
    > apiVersion: networking.istio.io/v1
    > kind: Gateway
    > metadata:
    >   name: <name>-gateway
    >   namespace: <namespace>
    > spec:
    >   selector:
    >     istio: <selector-label>
    >   servers:
    >   - hosts:
    >     - <hostname>
    >     name: <name>-gateway
    >     port:
    >       name: <name>-gatewayport443
    >       number: 443
    >       protocol: HTTPS
    >     tls:
    >       credentialName: <secret>
    >       mode: OPTIONAL_MUTUAL
    > ```

2.  Replace the placeholders with your specific values and save the file:

    -   *<name\>*, *<namespace\>*, and *<hostname\>*: Replace these with the values specific to your environment.
    -   *<selector-label\>*: Must match the selector label of the existing `default-gateway` resource. You can check this by executing the following command: `kubectl -n <namespace> get gateway default-gateway -o yaml`
    -   *<secret\>*: Must reference a secret name created specifically for this resource. If wildcard certificates are used, it can also refer to the secret used in `default-gateway`.

3.  Create the Istio gateway resource by executing the following command:kubectl apply -n <namespace\> -f gateway.yaml

    ```
    kubectl apply -n <namespace> -f gateway.yaml
    ```

4.  Create a second file named `virtualservice.yaml` and paste the following template:

    > ### Sample Code:  
    > ```
    > apiVersion: networking.istio.io/v1
    > kind: VirtualService
    > metadata:
    >   name: <name>-virtualservice
    >   namespace: <namespace>
    > spec:
    >   gateways:
    >   - <name>-gateway
    >   hosts:
    >   - <hostname>
    >   http:
    >   - match:
    >     - uri:
    >         prefix: /
    >     rewrite:
    >       authority: <default virtual host>
    >     route:
    >     - destination:
    >         host: policyengine.<namespace>.svc.cluster.local
    >         port:
    >           number: 8080
    > ```

5.  Replace the placeholders with your specific values and save the file:

    -   *<name\>*, *<namespace\>*, and *<hostname\>*: Replace these with the values specific to your environment.
    -   *<default virtual host\>*: Ensure that this exactly matches your actual Default Virtual Host.

6.  Create the Istio virtual service resource by executing the following command:

    > ### Sample Code:  
    > ```
    > kubectl apply -n <namespace> -f virtualservice.yaml
    > ```


