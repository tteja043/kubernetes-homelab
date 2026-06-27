# Kubernetes Homelab - Project 2: Nginx with ConfigMap

## Overview

This project is part of my Kubernetes Homelab series, built to gain hands-on experience with core Kubernetes concepts. The environment runs on **Minikube (Docker driver)** on macOS and demonstrates how an application is deployed, exposed, and configured using native Kubernetes resources.

In this project, I extended the initial Nginx deployment by introducing **ConfigMaps** to externalize application content. Instead of serving the default Nginx welcome page, the application now serves a custom HTML page stored in a Kubernetes ConfigMap.

---

## Technologies Used

* Kubernetes
* Minikube
* Docker
* kubectl
* Nginx

---

## Kubernetes Resources

### Namespace

A dedicated namespace (`homelab`) is used to isolate all project resources from the default namespace.

### Deployment

* Deploys multiple Nginx replicas.
* Ensures high availability and self-healing.
* Manages rolling updates when the deployment configuration changes.

### Service (NodePort)

* Exposes the Nginx application within the cluster.
* Allows external access for local development through a NodePort.

### Ingress

* Configured using the NGINX Ingress Controller.
* Routes HTTP traffic destined for `nginx.local` to the Nginx Service.
* Demonstrates hostname-based routing.

### ConfigMap

Stores the custom `index.html` page separately from the container image.

The ConfigMap is mounted into the container as a volume, replacing the default Nginx web page without rebuilding the Docker image.

---

## Architecture

```text
                Client
                   │
              Ingress
                   │
              NodePort Service
                   │
             Nginx Deployment
            ┌────────┴────────┐
         Nginx Pod        Nginx Pod
               │
      ConfigMap Volume Mount
               │
        Custom index.html
```

---

## Key Learning Objectives

* Creating and managing Kubernetes namespaces
* Deploying applications using Deployments
* Exposing applications using Services
* Configuring Ingress for HTTP routing
* Understanding Kubernetes networking
* Using ConfigMaps to externalize application configuration
* Mounting ConfigMaps as volumes inside containers
* Performing rolling updates after configuration changes
* Troubleshooting networking and Ingress behavior in a local Minikube environment

---

## Repository Structure

```text
kubernetes-homelab/
├── namespaces/
│   └── namespace.yaml
├── nginx/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   └── configmap.yaml
└── README.md
```

---

## Future Enhancements

* Persistent Volumes (PV) and Persistent Volume Claims (PVC)
* Secrets for sensitive configuration
* Helm chart packaging
* Prometheus and Grafana monitoring
* Argo CD for GitOps deployments
* Horizontal Pod Autoscaler (HPA)
* Network Policies
* CI/CD pipeline using GitHub Actions
