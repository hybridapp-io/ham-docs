# deployers.core.hybridapp.io

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Overview](#overview)
- [Specifications](#specifications)
  - [Deployer](#deployer)
  - [DeployerSet](#deployerset)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Overview

Resources of hybrid application are managed by existing systems (kubernetes, openstack, cloud service providers, ...) and capabilities of these systems are already bridged to kubernetes by our prerequisite. In Hybrid Application Model, we introduce "Deployer" Custom Resource to identify the instances of those essential parts of the hybrid environment. 
## Specifications

### Deployer

```yaml
apiVersion: core.hybridapp.io/v1alpha1
kind: Deployer
metadata:
  name: mykv
  namespace: vmsink8s
spec:
  type: kubevirt
  operatorRef:
    name:
    apiVersion:
    kind:
    namespace:
  capabilities:
  - verbs:
    apigroups:
    resources:
    resourceNames:
    nonResourceURLs:
  clusterScope: false
```

Here is the description to attributes in spec

| Attribute | Type | Required | Default Value | Description |
|-----------|------|----------|---------------|-------------|
| `type` | `string` | Y | N/A | Defined by user to identify the capability of this deployer |
| `operatorRef` | `v1.ObjectReference` | N | N/A | Point to the k8s resource represent the operator for this deployer instance |
| `capabilities` | `rbac.PolicyRule` | N | N/A | The resources and actions supported by this deployer instance |
| `clusterScope` | `bool` | Y | `false` | Indicates whether this deployer can only operate on the resources in its own namespace or not|

A hybrid environment consists of 1 or more Deployers, Deployer resource always sits in same k8s cluster with the actual operator perform the capabitilies of the system. 
