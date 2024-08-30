### Install KIND K8s 3 Node Cluster 


## Install Kind Utils 
```
sh k8s-install.sh
```

## Create KinD Clutser
```
kind create cluster --config=ingress-cluster.yaml
```

## Check the Cluster Status
```
kubectl cluster-info --context kind-app1-3-node-cluster
```
