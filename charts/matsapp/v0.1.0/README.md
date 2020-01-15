## Prerequisites

- Kubernetes 1.4+ with Beta APIs enabled
- a specified namespace named after one of the MATS build environments ["matsdev","matspreint","matsint","matsprod"]
- A preconfigured Persistent Volume minimum 10 GB.
- Only one matsmongo app per namespace is allowed
- The internal port must be left as 80
- an ingress will be established such that this app can be reaxhed from the outside via https.
- The ingres route will be https://{{host}}/{{buildEnvironment}}/home where {{host}} is the public address of your rancher deployment, and {{build environment}} is one of ["matsdev","matspreint","matsint","matsprod"] which should correspond to the namespace.

## Persistence
The same named PVC will be used for all MATSMONGO persisted data and will be shared with any [MATS](https://www.esrl.noaa.gov/gsd/mats) apps that are depoyed into the same namespace, and will be used by MATSHOME to create a landing page that accesses all MATS apps that are deployed to this namespace.