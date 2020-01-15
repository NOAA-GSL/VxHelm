#MATSMONGO
MATSMONGO is a streamlined version of MongoDB that is suitable for providing persistence for a suite of MATS apps.
This chart requires the pre-allocation of a Storage Class that the chart can use to allocate a dynamic Persistent Volume Claim.
A Persistent Volume Claim with minimum 10GB of storage space will be allocated for each namespace into
which MATSMONGO, a cooresponding MATSHOME, and a set of MATS apps are deployed. 
This volume claim will provide persistance for matsmongo and will also be shared to any MATS apps that are deployed into the same namespace.

The chart is intended to be deployed into a [Rancher](https://rancher.com/) environment.
## MongoDB
[MongoDB](https://www.mongodb.com/) is a cross-platform document-oriented database. Classified as a NoSQL database, MongoDB eschews the traditional table-based relational database structure in favor of JSON-like documents with dynamic schemas, making the integration of data in certain types of applications easier and faster.


## Introduction

This chart bootstraps a [MongoDB](https://github.com/bitnami/bitnami-docker-mongodb) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

Bitnami charts can be used with [Kubeapps](https://kubeapps.com/) for deployment and management of Helm Charts in clusters. This chart has been tested to work with NGINX Ingress, cert-manager, fluentd and Prometheus on top of the [BKPR](https://kubeprod.io/).
