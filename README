# Helm Chart Values Documentation

This README outlines the configuration options available in the Helm chart for Open Policy Agent (OPA) Gatekeeper policies, optimized for environments with several key policies enabled by default.

## Before deploy these policies

First install the OPA gatekeeper operator:
https://github.com/open-policy-agent/gatekeeper/blob/master/charts/gatekeeper/README.md

## Global Configuration

### Cloud Origin
Specifies the cloud provider environment.

- **Values**:
  - `cloudOrigin`: (string) The cloud provider. Possible values: `azure`, `aws`, `gcp`, `alibaba`, `digitalocean`, `oci`, `openstack`, `ibmcloud`. Default: `"azure"`

---

## Enabled Policies

### Privileged Containers
Restrict the use of privileged containers.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `excludedNamespaces`: (list) Namespaces exempt from this policy. Default: `["kube-system", "default"]`
  - `exemptImages`: (list) Container images exempt from this policy. Default: `[]`
- **Reference**: [Privileged Containers](https://open-policy-agent.github.io/gatekeeper-library/website/validation/privileged-containers/)

---

### Host Namespaces
Restrict usage of host namespaces.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `excludedNamespaces`: (list) Namespaces exempt from this policy. Default: `[]`
- **Reference**: [Host Namespaces](https://open-policy-agent.github.io/gatekeeper-library/website/validation/host-namespaces/)

---

### Privilege Escalation in Containers
Disallow privilege escalation within containers.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `exemptImages`: (list) Container images exempt from this policy. Default: `[]`
- **Reference**: [Privilege Escalation](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allow-privilege-escalation)

---

### Read-Only Root Filesystem
Enforce containers to use a read-only root filesystem.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `exemptImages`: (list) Container images exempt from this policy. Default: `[]`
- **Reference**: [Read-Only Root Filesystem](https://open-policy-agent.github.io/gatekeeper-library/website/validation/read-only-root-filesystem)

---

### Allowed Repositories
Restrict container images to specific repositories.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `repos`: (list) List of allowed repositories. Default: `["registry.k8s.io/", "nginx"]`
- **Reference**: [Allowed Repositories](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allowedrepos)

---

### Automount Service Account Token
Restrict automounting service account tokens.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `excludedNamespaces`: (list) Namespaces exempt from this policy. Default: `["kube-system"]`
- **Reference**: [Automount Service Account Token](https://open-policy-agent.github.io/gatekeeper-library/website/validation/automount-serviceaccount-token)

---

### Block NodePort Services
Prevent creation of NodePort services.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
- **Reference**: [Block NodePort](https://open-policy-agent.github.io/gatekeeper-library/website/validation/block-nodeport-services)

---

### Required Resources
Enforce requests and limits for CPU and memory in containers.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `limits`: (list) List of required limits. Default: `["cpu", "memory"]`
  - `requests`: (list) List of required requests. Default: `["cpu", "memory"]`
- **Reference**: [Required Resources](https://open-policy-agent.github.io/gatekeeper-library/website/validation/containerresources)

---

### Disallow Tags
Restrict usage of specific image tags.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `tags`: (list) List of disallowed tags. Default: `["latest"]`
  - `exemptImages`: (list) Container images exempt from this policy. Default: `[]`
- **Reference**: [Disallow Tags](https://open-policy-agent.github.io/gatekeeper-library/website/validation/disallowedtags)

---

### Container Ephemeral Storage Limit
Enforce limits on ephemeral storage for containers.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `ephemeralStorage`: (string) Maximum ephemeral storage allowed. Default: `"500Mi"`
  - `exemptImages`: (list) Container images exempt from this policy. Default: `[]`
- **Reference**: [Ephemeral Storage Limit](https://open-policy-agent.github.io/gatekeeper-library/website/validation/ephemeralstoragelimit)

---

### Replica Limits
Enforce minimum and maximum replicas for workloads.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`
  - `ranges`: (list) Define ranges for replicas. Default:
    ```yaml
    - min_replicas: 2
      max_replicas: 50
    ```
- **Reference**: [Replica Limits](https://open-policy-agent.github.io/gatekeeper-library/website/validation/replicalimits)

---

### Service Load Balancer Annotations
Enforce specific annotations for service load balancers.

- **Values**:
  - `enabled`: (bool) Enable or disable the policy. Default: `true`

---

## Partially Enabled or Disabled Policies

- **FS Group Policy**: Disabled. Enforces fsGroup rule and ranges. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/fsgroup)
- **Capabilities**: Disabled. Restricts Linux capabilities in containers. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/capabilities)
- **Disallowed Repositories**: Disabled. Prevents usage of specific repositories. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/disallowedrepos)
- **Horizontal Pod Autoscaler**: Disabled. Enforces scaling configuration for workloads. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/horizontalpodautoscaler)
- **Ingress HTTPS Only**: Disabled. Enforces HTTPS on ingress resources. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/httpsonly)
- **Image Digests**: Disabled. Enforces use of image digests. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/imagedigests)
- **Pod Disruption Budget**: Disabled. Enforces PodDisruptionBudget configurations. [Details](https://open-policy-agent.github.io/gatekeeper-library/website/validation/poddisruptionbudget)



# Helm Chart Values Table

| **Parameter**                                   | **Description**                                                                                           | **Default Value**                                  | **Reference URL**                                                                                                          |
|-------------------------------------------------|-----------------------------------------------------------------------------------------------------------|---------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `global.cloudOrigin`                            | Specifies the cloud provider environment.                                                                 | `"azure"`                                         | N/A                                                                                                                      |
| `privilegedContainer.enabled`                   | Restrict the use of privileged containers.                                                                | `true`                                            | [Privileged Containers](https://open-policy-agent.github.io/gatekeeper-library/website/validation/privileged-containers/) |
| `privilegedContainer.excludedNamespaces`        | Namespaces exempt from the privileged container policy.                                                   | `["kube-system", "default"]`                     | [Privileged Containers](https://open-policy-agent.github.io/gatekeeper-library/website/validation/privileged-containers/) |
| `privilegedContainer.exemptImages`              | Container images exempt from the privileged container policy.                                             | `[]`                                             | [Privileged Containers](https://open-policy-agent.github.io/gatekeeper-library/website/validation/privileged-containers/) |
| `hostNamespace.enabled`                         | Restrict usage of host namespaces.                                                                        | `true`                                            | [Host Namespaces](https://open-policy-agent.github.io/gatekeeper-library/website/validation/host-namespaces/)             |
| `hostNamespace.excludedNamespaces`              | Namespaces exempt from the host namespace policy.                                                         | `[]`                                             | [Host Namespaces](https://open-policy-agent.github.io/gatekeeper-library/website/validation/host-namespaces/)             |
| `privilegeEscalationContainer.enabled`          | Restrict privilege escalation in containers.                                                              | `true`                                            | [Privilege Escalation](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allow-privilege-escalation) |
| `privilegeEscalationContainer.exemptImages`     | Container images exempt from the privilege escalation policy.                                             | `[]`                                             | [Privilege Escalation](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allow-privilege-escalation) |
| `readOnlyRootFilesystem.enabled`               | Enforce containers to use read-only root filesystems.                                                     | `true`                                            | [Read-Only Root Filesystem](https://open-policy-agent.github.io/gatekeeper-library/website/validation/read-only-root-filesystem) |
| `readOnlyRootFilesystem.exemptImages`          | Container images exempt from the read-only root filesystem policy.                                        | `[]`                                             | [Read-Only Root Filesystem](https://open-policy-agent.github.io/gatekeeper-library/website/validation/read-only-root-filesystem) |
| `allowedRepositories.enabled`                   | Restrict container images to specific repositories.                                                       | `true`                                            | [Allowed Repositories](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allowedrepos)            |
| `allowedRepositories.repos`                     | List of allowed repositories for container images.                                                        | `["registry.k8s.io/", "nginx"]`                  | [Allowed Repositories](https://open-policy-agent.github.io/gatekeeper-library/website/validation/allowedrepos)            |
| `automountServiceAccountTokenForPod.enabled`    | Restrict automounting service account tokens in pods.                                                     | `true`                                            | [Automount Service Account Token](https://open-policy-agent.github.io/gatekeeper-library/website/validation/automount-serviceaccount-token) |
| `automountServiceAccountTokenForPod.excludedNamespaces` | Namespaces exempt from the automount service account token policy.                                        | `["kube-system"]`                                | [Automount Service Account Token](https://open-policy-agent.github.io/gatekeeper-library/website/validation/automount-serviceaccount-token) |
| `BlockNodePort.enabled`                         | Block usage of NodePort services.                                                                         | `true`                                            | [Block NodePort](https://open-policy-agent.github.io/gatekeeper-library/website/validation/block-nodeport-services)        |
| `RequiredResources.enabled`                     | Enforce resource requests and limits for containers.                                                      | `true`                                            | [Required Resources](https://open-policy-agent.github.io/gatekeeper-library/website/validation/containerresources)         |
| `RequiredResources.limits`                      | List of resource limits to enforce.                                                                       | `["cpu", "memory"]`                              | [Required Resources](https://open-policy-agent.github.io/gatekeeper-library/website/validation/containerresources)         |
| `RequiredResources.requests`                    | List of resource requests to enforce.                                                                     | `["cpu", "memory"]`                              | [Required Resources](https://open-policy-agent.github.io/gatekeeper-library/website/validation/containerresources)         |
| `DisallowTags.enabled`                          | Restrict the use of specific image tags.                                                                  | `true`                                            | [Disallow Tags](https://open-policy-agent.github.io/gatekeeper-library/website/validation/disallowedtags)                 |
| `DisallowTags.tags`                             | List of disallowed tags.                                                                                   | `["latest"]`                                     | [Disallow Tags](https://open-policy-agent.github.io/gatekeeper-library/website/validation/disallowedtags)                 |
| `ReplicaLimits.enabled`                         | Enforce replica count ranges for workloads.                                                               | `true`                                            | [Replica Limits](https://open-policy-agent.github.io/gatekeeper-library/website/validation/replicalimits)                 |
| `ReplicaLimits.ranges`                          | Define ranges for replica counts.                                                                         | `[{"min_replicas": 2, "max_replicas": 50}]`      | [Replica Limits](https://open-policy-agent.github.io/gatekeeper-library/website/validation/replicalimits)                 |
| `SvcLoadbalancerAnnotations.enabled`            | Enforce annotations on Service type LoadBalancer.                                                         | `true`                                            | N/A                                                                                                                      |

*(Continue adding entries for all other parameters.)*
