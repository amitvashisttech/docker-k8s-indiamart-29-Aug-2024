# Creating out First App

## Check the health of Cluster
```
kubectl get nodes
```

## Deploy Nginx App
```
kubectl run hello-k8s --image=nginx --port=80
```

## Check the status of PODs
```
kubectl get pods
kubectl describe pods hello-k8s
```

