# Core of Hybrid Applicaiton Model

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Outline](#outline)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Outline

The Application definition from Kubernetes Special Interest Group serves this purpose well, **applications.app.k8s.io/v1beta1** is the first resource we introduce into hybrid application model.

[**deployables.core.hybridapp.io/v1alph1**](deployable.md) is introduced to wrap resource inside it.

**subscriptions.apps.open-cluster-management.io** is leveraged to point to resources outside kubernetes.

[**deployers.core.hybridapp.io/v1alph1**](deployer.md) is intrdoduced to model various systems working with actual resources

**placementrue.apps.open-cluster-management.io** is leveraged to describe which deployer is used in deploying resources.

