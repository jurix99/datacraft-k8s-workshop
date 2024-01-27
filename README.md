# ClimateQA Kubernetes Project

## Overview

ClimateQA Kubernetes project is aimed at providing a scalable and reliable platform for asking questions about the environment. Leveraging Kubernetes, this project ensures seamless deployment, management, and scaling of the chat application dedicated to environmental queries.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed:

- [Chocolatey](https://chocolatey.org/install): Chocolatey is a package manager for Windows. Install it to easily manage software dependencies.
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/): Kubernetes command-line tool. Install it via Chocolatey:
```bash
choco install minikube
```
- [Minikube](https://minikube.sigs.k8s.io/docs/start/): Local Kubernetes cluster management tool. Install it via Chocolatey:
```bash
choco install kubernetes-cli
```

## Deployment

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone <repository_url>
cd datacraft-k8s-workshop
```

Start Minikube
```
minikube start
```
### 2. Apply Kubernetes Manifests
Apply the Kubernetes manifests for deploying ClimateQA components:

```
kubectl apply -f namespaces.yaml
kubectl apply -f ./qdrant
kubectl apply -f ./chat
kubectl apply -f ingress.yaml
```

Access your app
```
minikube service qa-service
```

This will deploy the necessary pods and services for running the ClimateQA chat application.

## Usage
Once the deployment is successful, you can interact with the ClimateQA chat application. Use the following commands to monitor the pods and deployments:

```
kubectl get pods -n climateqa
kubectl get deployments -n climateqa
```