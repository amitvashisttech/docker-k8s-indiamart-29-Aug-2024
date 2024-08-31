# NameSpace 

### List all the namespace 
```
kubectl get ns 
```

### Create a new namespace via command
```
kubectl create ns test
```

### Deploy the pods & check in which namespace its deployed. 
```
kubectl create -f 1-helloworld.yaml
```

```
kubectl get pods --all-namespaces
```

### Deploy the pods in test namespaces 
```
kubectl  create  -f 1-helloworld.yaml -n test
```
```
kubectl get pods --all-namespaces
```
```
kubectl get pods -n test
```
```
kubectl get pods -n test
NAME                                     READY   STATUS    RESTARTS   AGE
helloworld-deployment-7d8fcf8bdc-5mvch   1/1     Running   0          45s
helloworld-deployment-7d8fcf8bdc-9bs7b   1/1     Running   0          45s
helloworld-deployment-7d8fcf8bdc-rqfgz   1/1     Running   0          45s
```


### Delete the namespace 
```
kubectl delete ns test
```

### Deploy the namespace form a YAML
```
kubectl create -f 2-Namespace-defination.yaml 
```

### Deploy deployment to specific namespace
```
kubectl  create -f 3-helloworld-with-ns.yaml
```


### Clean UP
```
cd ..
kubectl delete -f 09-Namespaces/
```

