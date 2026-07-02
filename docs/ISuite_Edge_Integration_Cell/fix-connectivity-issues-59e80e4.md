<!-- loio59e80e407bf04855898e1029aa90061b -->

# Fix Connectivity Issues

Check and fix connectivity issues.



<a name="loio59e80e407bf04855898e1029aa90061b__prereq_s12_wqs_nvb"/>

## Prerequisites

You've checked the following:

-   You've created a keypair for the `default virtual host` and the keypair is available in *Security Material* section.

-   You've entered a keypair alias name during solution deployment.




## Procedure

If the Edge Integration Cell solution deployment finished successfully, but the connection to the Edge Integration Cell fails with a timeout or a connect error, try the following steps:

1.  **Lookup DNS entry** 

    To check if the DNS entry can be resolved as expected, use your shell command line to enter `nslookup <default virtual host>`.

2.  **Check connectivity**

    To check the connectivity, use your shell command line to enter the command `openssl s_client -connect <default virtual host>:443`, or `curl -vk https://<default virtual host>`.

3.  **Check Ingress Gateway** 

    To check the Ingress Gateway, use the kubectl tool to enter the command: `kubectl get gateway -n edge-icell`. The output is a gateway called `default-gateway`.

    In addition, verify the existence of the Ingress Virtual Service, using the following command: `kubectl get virtualservice -n edge-icell -o yaml`. The The output is a Virtual Service called `<default-virtualservice>`.

    > ### Note:  
    > If the Gateway `<default-gateway>` and the Virtual Service `<default-virtualservice>` do not exist, exceute the following commands:
    > 
    > 1.  Restart Edge Event Controller pod. `kubectl rollout restart deployment/edc -n edge-icell`
    > 
    > 2.  Restart Policy Engine Pod. `kubectl rollout restart deployment/policyengine -n edge-icell`

    -   Then recheck the existence of the Gateway and the Virtual Service as described in step 3.
    -   If the Gateway `<default-gateway>` and virtual service `<default-vitualservice>` do not exist, open a ticket on component BC-CP-IS-EDG-DPL, and attach the diagnostics file or the Edge Deploy Controller log. You can create the diagnostics file via Edge LM UI.
    -   To get the Edge Deploy Controller log, first identify the Edge Deploy Controller pod by entering `kubectl get pod -n edge-icell` in the kubectl tool. Then get the Edge Deploy Controller log by entering `kubectl logs <edc-pod> -n edge-icell` in the kubectl tool.


