<!-- loio2557e81529d6449a898a610467b5d5ae -->

# Pod Security Standards

Edge Integration Cell aims to meet Pod Security Standards by adapting to Gatekeeper security policies, which also form the basis for Azure Policy. For more information about Gatekeeper and Azure Policy, see[Gatekeeper](https://open-policy-agent.github.io/gatekeeper/website/), [Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/concepts/policy-for-kubernetes).

Compared to K8s Pod Security Admission, Gatekeeper policies allow for a more fine-grained configuration based on Constraint Templates and Constraints. For more information, see[Pod Security Admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/).

Istio is used as a central component for ingress handling and mTLS enablement within the K8s cluster. With its sidecar concept, Istio has special requirements when it comes to Pod Security Standards. For more information, see [Pod Requirements](https://istio.io/latest/docs/ops/deployment/application-requirements/#pod-requirements).

The following table specifies required exemptions for individual pods or containers from Gatekeeper's standard policy library. Some of the constraints are application-specific, such as K8sPSPAllowedUsers or K8sReplicaLimits, and are questionable to be set at a generic level.


<table>
<tr>
<th valign="top">

Constraint

</th>
<th valign="top">

Exemptions

</th>
<th valign="top">

Reason

</th>
</tr>
<tr>
<td valign="top">

K8sContainerEphemeralStorageLimit

</td>
<td valign="top">

worker

istio-init, istio-proxy

</td>
<td valign="top">

Worker pods require higher ephemeral storage for streaming larger messages.

The Istio configuration currently has no ephemeral storage limit.

</td>
</tr>
<tr>
<td valign="top">

K8sContainerLimits

</td>
<td valign="top">

edc, edge-api, edge-event-controller, esac, mdc, policyengine, solops, ssb-operator-manager, ssb-solace, worker

internal: postgres, redis

</td>
<td valign="top">

Edge Integration Cell pods have higher CPU and memory limits.

Maximum CPU limit: 2000m

Maximum memory limit: 4096Mi

Limits may depend on runtime parameter settings for a component.

</td>
</tr>
<tr>
<td valign="top">

K8sContainerRatios

</td>
<td valign="top">

edc, edge-api, edge-event-controller, ela-server, esac, mdc, policyengine, solops, ssb-operator-manager, ssb-solace, worker

istio-init, istio-proxy

internal: postgres, postgres-exporter, redis

</td>
<td valign="top">

Edge Integration Cell pods, including Istio, have higher CPU and memory limit ratios.

</td>
</tr>
<tr>
<td valign="top">

K8sContainerRequests

</td>
<td valign="top">

edc, edge-event-controller, policyengine, ssb-solace, worker

</td>
<td valign="top">

Edge Integration Cell pods have higher CPU and memory requests.

Max CPU request: 1000m

Max memory request: 3.4Gi

</td>
</tr>
<tr>
<td valign="top">

K8sHorizontalPodAutoscaler

</td>
<td valign="top">

edc, policyengine

</td>
<td valign="top">

Edge Integration Cell pods have different ranges \(minReplicas, maxReplicas\).

</td>
</tr>
<tr>
<td valign="top">

K8sPSPAllowedUsers

</td>
<td valign="top">

all

</td>
<td valign="top">

Edge Integration Cell components run with specified users, groups, supplementalGroups.

</td>
</tr>
<tr>
<td valign="top">

K8sPSPAutomountServiceAccountTokenPod

</td>
<td valign="top">

edc, edge-api, ela-server, solops, ssb-operator-manager, ssb-solace

</td>
<td valign="top">

Edge Integration Cell components need access to Kubernetes API server.

</td>
</tr>
<tr>
<td valign="top">

K8sPSPFSGroup

</td>
<td valign="top">

edc, edge-event-controller, policyengine, ssb-solace

</td>
<td valign="top">

Edge Integration Cell components run with specified fsGroup.

</td>
</tr>
<tr>
<td valign="top">

K8sPSPReadOnlyRootFilesystem

</td>
<td valign="top">

edge-api, edge-event-controller, esac, mdc, ssb-solace, worker

istio-init

internal: postgres

</td>
<td valign="top">

Edge Integration Cell components, including Istio, require a writable filesystem.

</td>
</tr>
<tr>
<td valign="top">

K8sReplicaLimits

</td>
<td valign="top">

all

</td>
<td valign="top">

Edge Integration Cell components have specified replica settings.

</td>
</tr>
<tr>
<td valign="top">

K8sRequiredAnnotations

</td>
<td valign="top">

all

</td>
<td valign="top">

Edge Integration Cell components do not use the annotations a8r.io/owner and a8r.io/runbook.

</td>
</tr>
<tr>
<td valign="top">

K8sRequiredProbes

</td>
<td valign="top">

ela-server \(kube-mgmt\), ssb-solace \(proexso\), worker \(log-extractor\)

istio-proxy

</td>
<td valign="top">

Selected containers do not require a readiness probe for technical reasons.

</td>
</tr>
</table>

For details on the Edge Lifecycle Management components, see [Required Gatekeeper Constraints](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/c84d220f63d6480a8554b24b50fa6508.html).

