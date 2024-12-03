# Cosmocloud Helm Chart

This Helm chart deploy a complete application consisting of:

- A Backend service
- A Frontend service
- A Redis database

This chart deploy application with much ease.


# Chart Functionality

### The cosmocloud-deploy Helm chart have:

## Backend Service:
- Deploys the backend of application from the shreybatra/sample-backend image.
- Set an environment variable REDIS_URI for Redis connectivity.
- Exposed internally using a ClusterIP service on port 8000.

## Frontend Service:
- Deploys the frontend of application from the image shreybatra/sample-frontend.
- Configures an environment variable BACKEND_URL for connection to the backend.
- Exposed externally using a NodePort service on port 31000.

## Redis Database:
- Deploys the Redis database using the official redis image.
- Exposed internally using a ClusterIP service on port 6379.


# Steps to Deploy

## Clone the Repository

```bash
git clone https://github.com/vivekpyadav/cosmocloud-deploy.git
```

Verify Kubernetes Cluster Ensure your Kubernetes cluster is running and configured:
```bash
kubectl get nodes
```
Deploy the Chart Install the Helm chart:
```bash
helm install testapp cosmocloud-deploy --atomic --timeout 30s
```
Verify Deployment Check that the pods and services are running:
```bash
kubectl get pods
kubectl get services
```
