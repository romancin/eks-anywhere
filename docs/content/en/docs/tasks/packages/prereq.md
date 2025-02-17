---
title: "Package Prerequisites"
linkTitle: "Package Prerequisites"
weight: 10
description: >
  Prerequisites for using curated packages
---

## Prerequisites
Before installing any curated packages for EKS Anywhere, do the following:

* Check that the version of `eksctl anywhere` is `v0.11.0` or above with the `eksctl anywhere version` command.
* Make sure cert-manager is up and running in the cluster. Note cert-manager is not installed on workload clusters by default. If cert-manager is not installed, you can manually install cert-manager and follow the instructions below to finish the package controller installation.
* Check the existence of package controller:
    ```bash
    kubectl get pods -n eksa-packages | grep "eks-anywhere-packages"
    ```
    If the returned result is empty, you need to install the package controller.

* Install the package controller if it is not installed:
    Install the package controller
     
     *Note* This command is temporarily provided to ease integration with curated packages. This command will be deprecated in the future
 
     ```bash
     eksctl anywhere install packagecontroller -f $CLUSTER_NAME.yaml
     ```
