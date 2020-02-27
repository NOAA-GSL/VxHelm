## Prerequisites

- Kubernetes 1.4+ with Beta APIs enabled
- a specified namespace named after one of the MATS build environments ["matsdev","matspreint","matsint","matsprod"]
- A preconfigured Storage Class suitable for creating a Persistent Volume Claim of 10 GB.
- The deployment of a matsmongo into the target namespace.
- Only one MATSHOME app per MATS namespace is allowed
- The internal port must be left as 80
- an ingress will be established such that this app can be reached from the outside via https.
- The ingres route will be https://{{host}}/{{buildEnvironment}}/home where {{host}} is the public address of your rancher deployment, and {{build environment}} is one of ["matsdev","matspreint","matsint","matsprod"] which should correspond to the namespace.

## Persistence
The same dynamically created PVC will be used for all MATSMONGO persisted data and will be shared with any [MATS](https://www.esrl.noaa.gov/gsd/mats) apps that are deployed into the same namespace, and will also be used by MATSHOME to create a landing page that accesses all MATS apps that are deployed to this namespace.