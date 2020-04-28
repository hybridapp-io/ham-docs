# Dcouments for Hybrid Application Model

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [What's New](#whats-new)
- [Motications](#motications)
- [Overview](#overview)
- [Specifications](#specifications)
  - [core](#core)
  - [tools](#tools)
  - [deploy](#deploy)
  - [integration](#integration)
- [Community](#community)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## What's New

Hello, world!

## Motications

Container platforms has become an integral part of modern IT landscape, but the majority of the systems in the world are still built on legacy technologies. Here we introduce a hybrid application model to improve the management efficiency of assets across various platforms (containers, virtual machines, cloud services, ...)

## Overview

Term "Application" in this model refers to a group of resources, those resources are managed in various systems (kubernetes, openstack, manageiq, cloud services, ... ). Each system has its own way to define the resources it manages, there are overlaps as well as conflicts across systems.

The goal of this model is to provide a common way to define resources of hybrid application with their deployment information, so that they can be discovered or distributed across systems and managed in a centralized way. 

This model is implemented in kubernetes with its Custom Resource technology, and leverages other assets in kubernetes.

## Specifications

This specification consists of fllowing sections:

### core

The core section defines the essential resources to describe hybrid environment and the resources in it. All custom resources introduced in this section sit in `core.hybridapp.io` group. 

### tools

The tools section defines useful tools to facilitate the usage of hybrid application model. All custom resources introduced in this section sit in `tools.hybridapp.io` group.

### deploy

The deploy section describes how to deploy/install this model into a hybrid environment

### integration

The integration section defines how this model interacts with those systems managing actual resources. 

## Community
