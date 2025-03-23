# CLO835 - Assignment 2

This repository contains Kubernetes manifests for deploying a two-tier web application with a MySQL database backend.

## Structure

- `k8s/pod/`: Pod manifests for MySQL and Web Application
- `k8s/replicaset/`: ReplicaSet manifests
- `k8s/deployment/`: Deployment manifests
- `k8s/service/`: Service manifests

## Prerequisites

- Kubernetes cluster (using kind or any other Kubernetes distribution)
- kubectl configured to communicate with your cluster

## Resource Considerations

All manifests include resource constraints to prevent environment overload:
- MySQL containers: Resource requests of 100m CPU and 100Mi memory
- Web application containers: Resource requests of 100m CPU and 100Mi memory

## Deployment Steps

1. Create namespaces
```
kubectl apply -f k8s/namespace.yaml
```

2. Deploy pods
```
kubectl apply -f k8s/pod/
```

3. Deploy ReplicaSets
```
kubectl apply -f k8s/replicaset/
```

4. Deploy applications with Deployments
```
kubectl apply -f k8s/deployment/
```

5. Expose services
```
kubectl apply -f k8s/service/
```

## Application Access

The web application is accessible on NodePort 30000.

## Update Process

To update the application, simply update the deployment manifest and apply it:
```
kubectl apply -f k8s/deployment/webapp-deployment-v2.yaml
```
