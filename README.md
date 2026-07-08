# Kubernetes Homelab

## Overview

This repository documents my hands-on Kubernetes learning journey using a local homelab built with **Minikube**. The goal is to gain practical experience with core Kubernetes concepts by building, deploying, and managing applications while following production-oriented best practices.

Each project builds upon the previous one, introducing a new Kubernetes concept and demonstrating how different resources work together.

---

## Environment

* Kubernetes (Minikube)
* Docker Driver
* macOS
* kubectl
* NGINX

---

# Project Roadmap

| Project     | Status    | Topics Covered                                                              |
| ----------- | --------- | --------------------------------------------------------------------------- |
| ✅ Project 1 | Completed | Namespace, Deployment, Service, Ingress                                     |
| ✅ Project 2 | Completed | ConfigMaps, Volume Mounts, Custom NGINX Homepage                            |
| ✅ Project 3 | Completed | Persistent Volumes (PV), Persistent Volume Claims (PVC), Persistent Storage |
| ⏳ Project 4 | Planned   | Kubernetes Secrets                                                          |
| ⏳ Project 5 | Planned   | Helm Charts                                                                 |
| ⏳ Project 6 | Planned   | Prometheus & Grafana                                                        |
| ⏳ Project 7 | Planned   | Argo CD (GitOps)                                                            |

---

# Project 1 – Deploying NGINX

## Objective

Deploy a highly available NGINX application on Kubernetes and expose it using Kubernetes networking resources.

### Kubernetes Resources

* Namespace
* Deployment
* Service
* Ingress
* NGINX Ingress Controller

### What I Learned

* Creating and managing Namespaces
* Deploying applications using Deployments
* Managing multiple Pod replicas
* Exposing applications using Services
* Configuring Ingress resources
* Understanding Kubernetes networking
* Troubleshooting Ingress and Minikube networking

---

# Project 2 – ConfigMaps

## Objective

Externalize application configuration by replacing the default NGINX welcome page with a custom HTML page stored in a Kubernetes ConfigMap.

### Kubernetes Resources

* ConfigMap
* Deployment (updated)
* Service
* Ingress

### Implementation

* Created a ConfigMap containing a custom `index.html`.
* Mounted the ConfigMap into the NGINX container.
* Replaced the default NGINX page without rebuilding the container image.

### What I Learned

* Separating configuration from application images
* Mounting ConfigMaps as volumes
* Managing application configuration in Kubernetes
* Rolling out Deployment updates after configuration changes

---

# Project 3 – Persistent Storage

## Objective

Understand how Kubernetes provides persistent storage that survives Pod restarts and recreations.

### Kubernetes Resources

* Persistent Volume (PV)
* Persistent Volume Claim (PVC)
* Deployment (updated)

### Implementation

* Created a Persistent Volume.
* Created a Persistent Volume Claim.
* Mounted the PVC into the NGINX container.
* Created the website content directly on the mounted volume.
* Verified that the content persisted after deleting and recreating Pods.

### What I Learned

* Difference between ephemeral and persistent storage
* Persistent Volumes and Persistent Volume Claims
* Volume mounting in Kubernetes
* Data persistence across Pod recreation
* Relationship between Pods, PVCs, and PVs

---

# Architecture Evolution

### Project 1

```text
Client
   │
Ingress
   │
Service
   │
Deployment
   │
Pods
```

### Project 2

```text
ConfigMap
     │
Mounted into
     │
NGINX Pod
```

### Project 3

```text
Persistent Volume
        │
Persistent Volume Claim
        │
Mounted into
        │
NGINX Pod
```

---

# Repository Structure

```text
kubernetes-homelab/
├── namespaces/
├── nginx/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   ├── configmap.yaml
│   ├── pv.yaml
│   ├── pvc.yaml
│   └── README.md
├── docs/
│   ├── project-1.md
│   ├── project-2.md
│   └── project-3.md
└── README.md
```

---

# Key Skills Demonstrated

* Kubernetes resource management
* Application deployments
* Service discovery
* Ingress configuration
* Configuration management using ConfigMaps
* Persistent storage using PVs and PVCs
* Volume mounts
* Kubernetes networking
* Troubleshooting Kubernetes workloads in a local Minikube environment

---

# Future Enhancements

* Kubernetes Secrets
* Helm Charts
* StatefulSets
* Prometheus
* Grafana
* Loki
* Argo CD
* GitHub Actions CI/CD
* Horizontal Pod Autoscaler (HPA)
* Network Policies
* Multi-container Pods
* Kubernetes Operators

---

## Learning Outcome

This repository is being developed as a progressive Kubernetes homelab to strengthen practical Kubernetes administration skills through hands-on projects. Each project builds on previous concepts while introducing new Kubernetes resources and operational practices commonly used in production environments.
