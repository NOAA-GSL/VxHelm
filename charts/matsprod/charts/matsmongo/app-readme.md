# MATSMONGO
MATSMONGO is a streamlined installation of a standard MongoDB that is suitable for providing persistence for a suite of MATS apps.
This chart requires the pre-allocation of a Persistent Volume Claim, with minimum 10GB of storage space, allocated for each namespace that is to be used for MATS apps.
This volume claim will provide persistance for mongo and should also be shared to any MATS apps (including matshome) that are deployed into the same namespace.

The chart is intended to be deployed into a [Rancher](https://rancher.com/) environment.
## MongoDB
[MongoDB](https://www.mongodb.com/) is a cross-platform document-oriented database. Classified as a NoSQL database, MongoDB eschews the traditional table-based relational database structure in favor of JSON-like documents with dynamic schemas, making the production of data in certain types of applications easier and faster.

## Namespace
MATS apps are generally deployed into their own specific namespace. A MATS deployment will consist of
1. one MATSMONGO app
1. one MATSHOME app
1. some number of MATS apps

All of these apps will use the same pre-allocated Persistent Volume Claim.
## Introduction

This chart bootstraps a [MongoDB](https://github.com/bitnami/bitnami-docker-mongodb) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

Bitnami charts can be used with [Kubeapps](https://kubeapps.com/) for deployment and management of Helm Charts in clusters. This chart has been tested to work with NGINX Ingress, cert-manager, fluentd and Prometheus on top of the [BKPR](https://kubeprod.io/).
