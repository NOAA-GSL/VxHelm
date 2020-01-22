## Prerequisites

- Kubernetes 1.4+ with Beta APIs enabled
- a specified namespace named after one of the MATS build environments ["matsdev","matspreint","matsint","matsprod"]
- A preconfigured Storage Class suitable for creating a Persistent Volume Claim of 10 GB.
- Only one matsmongo app per namespace is allowed and only one Persistent Volume Claim should be used and shared between matsmongo, matshome, and any matsapps.
- The internal port must be left as 27017 (the standard mongoport)
- The external port will be set to CLUSTERIP so that this database can be reached from the outside by determining the public IP of the cluster, and the public port of the mongo service.
- Assuming the namespace is matsprod, use this technique to connect a mongo client ...
```node=$(rancher kubectl -n matsprod get nodes | grep worker | head -1 | awk '{print $1}' | awk '{$1=$1};1')
host=$(rancher kubectl -n matsprod describe nodes ${node} | grep public-ip | awk -F':' '{print $2}' | awk '{$1=$1};1')
port=$(rancher kubectl -n matsprod get services | grep mongo-nodeport | awk -F'[/:]' '{print $2}' | awk '{$1=$1};1')
mongo mongodb://${host}:${port}${db}
```

## Persistence
The PVC will be used for all mongo persisted data and will be shared with any [MATS](https://www.esrl.noaa.gov/gsd/mats) apps that are deployed into the same namespace.
