# deployables.core.hybridapp.io

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Overview](#overview)
- [Specification](#specification)
- [Status](#status)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Overview

Hybrid Deployable is the resource we introduced to model resource without impacting the kubernetes system hosting application model.

## Specification

``` yaml
apiVersion: core.hybridapp.io/v1alpha1
kind: Deployable
metadata:
  name: database
  namespace: workspace
spec:
  hybridtemplates:
  - deployerType: kubernetes
    template:
      apiVersion: apps/v1
      kind: Deployment
      spec:
      ...
  - deployerType: kubevirt
    template:
      apiVersion: kubevirt.io/v1alph1
      kind: VirtualMachine
      spec:
      ...
  - deployerType: cloudforms
    template:
      apiVersion: cloudform.ibm.com/v1
      kind: VirtualMachine
      spec:
      ...
  placement:
    deployers:
    - name:
    deployerLabels:
      matchLabels:
      matchExpressions:
    placementRef:
      name:
  overrides:
  dependencies:
```

Here is the description to attributes in spec

| Attribute | Type | Required | Default Value | Description |
|-----------|------|----------|---------------|-------------|
| `hybridtemplates` | `array` | Y | N/A | Defined the template to deploy the resources for each deployer type |
| `placement` | `object` | N | N/A | Define where to place the resource |
| `placement.deployers` | `[]v1.ObjectRefernce` | N | N/A | list of deployers to go |
| `placement.deployerLabels` | `metav1.labelSelector` | N | N/A | list of deployers to go |
| `overrides` | `array` | N | N/A | customize the template for specific deployer |
| `dependencies` | `array` | N | N/A | define resource to be deployed togethe |

## Status

