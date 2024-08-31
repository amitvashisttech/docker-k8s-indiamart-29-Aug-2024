# Kubernetes Nginx Configuration and Deployment

## This repository contains configurations and manifests to set up an Nginx server on a Kubernetes cluster. The steps include creating a ConfigMap for the Nginx configuration, deploying an Nginx pod, and exposing it via a service.
## Files in this Repository

    ### 1-ConfigMap.yaml: Contains the ConfigMap for the Nginx configuration.
    ### reverseproxy.conf: Nginx configuration file.
    ### 2-nginx-pod.yml: Kubernetes pod configuration for Nginx.
    ### 3-nginx-service.yaml: Kubernetes service configuration to expose the Nginx pod.

## Steps to Deploy Nginx on Kubernetes
### 1. Create ConfigMap

First, we need to create a ConfigMap that will hold the Nginx configuration.

```

cat reverseproxy.conf
```

Create the ConfigMap:

```

kubectl create configmap nginx-config --from-file=reverseproxy.conf --dry-run -o yaml > 1-ConfigMap.yaml
```

Apply the ConfigMap:

```

kubectl apply -f 1-ConfigMap.yaml
```

Verify the ConfigMap:

```

    kubectl get configmaps
```

### 2. Deploy Nginx Pod

Next, create and deploy the Nginx pod using the configuration in 2-nginx-pod.yml.

View the Pod Configuration File:

 ```

cat 2-nginx-pod.yml
```
Apply the Pod Configuration:

```

kubectl apply -f 2-nginx-pod.yml
```
Verify the Pod is Running:

```

kubectl get pods
```
### 3. Expose the Nginx Pod via a Service

To expose the Nginx pod, we will create a Kubernetes service using the configuration in 3-nginx-service.yaml.

View the Service Configuration File:

```

cat 3-nginx-service.yaml
```
Apply the Service Configuration:

```
kubectl apply -f 3-nginx-service.yaml
```

Verify the Service:

```

kubectl get svc
```

Describe the Service for More Details:

```
kubectl describe svc helloworld-nginx-service
```

### 4. Access the Nginx Pod

To access the Nginx pod and verify the configuration:

Describe the Nginx Pod:

```

kubectl describe pod helloworld-nginx
```
Execute a Bash Shell in the Nginx Pod:

```

kubectl exec -it helloworld-nginx -c nginx -- bash
```
