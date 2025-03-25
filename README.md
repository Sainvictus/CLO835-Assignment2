# CLO835 - Assignment 2

This repository contains Kubernetes manifests for deploying a two-tier web application with a MySQL database backend.

## Structure

- `k8s/pod/`: Pod manifests for MySQL and Web Application
- `k8s/replicaset/`: ReplicaSet manifests
- `k8s/deployment/`: Deployment manifests
- `k8s/service/`: Service manifests

## Prerequisites

- Kubernetes cluster (using kind)
- kubectl
- ECR Registery

## Deployment Steps

1. Create namespaces
```
kubectl apply -f k8s/namespace.yaml
```

2. Expose services 
```
kubectl apply -f k8s/service/
```

3. Deploy pods
```
kubectl apply -f k8s/pod/
```

4. Deploy ReplicaSets
```
kubectl apply -f k8s/replicaset/
```

5. Deploy applications with Deployments
```
kubectl apply -f k8s/deployment/
```

## Application Access

The web application is accessible on NodePort 30000.

## Update Process

To update the application, simply update the deployment manifest and apply it:
```
kubectl apply -f k8s/deployment/employapp-deployment-v2.yaml
```
