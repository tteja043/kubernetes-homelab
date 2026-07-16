# Kubernetes Homelab 🚀

A hands-on Kubernetes Homelab built using **Minikube** to learn Kubernetes, Helm, GitOps, storage, networking and platform engineering concepts.

The objective of this repository is to build production-ready Kubernetes skills by implementing real-world projects and following Infrastructure as Code (IaC) and GitOps best practices.

---

# 🛠️ Tech Stack

- Kubernetes (Minikube)
- Docker Desktop
- kubectl
- Helm
- Argo CD
- NGINX
- VS Codium
- Git & GitHub

---

# 📂 Repository Structure

```
homelab/
│
├── argocd/
│   ├── application.yaml
│   └── README.md
│
├── docs/
│
├── helm/
│   └── nginx/
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
│
├── manifests/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   ├── configmap.yaml
│   ├── pv.yaml
│   ├── pvc.yaml
│   └── secret.yaml
│
├── monitoring/
│
├── README.md
└── .gitignore
```

---

# 🚀 Projects

## ✅ Project 1 - Kubernetes Basics

### Objective
Deploy a simple NGINX application on Kubernetes.

### Concepts

- Namespace
- Deployment
- ReplicaSets
- Pods
- Labels & Selectors
- ClusterIP Service
- NodePort Service
- Ingress
- Minikube

### Outcome

- Deployed NGINX with multiple replicas.
- Exposed the application using Services and Ingress.
- Configured local DNS (`nginx.local`).
- Learned Kubernetes networking fundamentals.

---

## ✅ Project 2 - ConfigMaps

### Objective

Separate application configuration from the container image.

### Concepts

- ConfigMaps
- Volume Mounts
- Configuration Management

### Outcome

- Created a custom HTML page.
- Mounted ConfigMap into the NGINX container.
- Updated application content without rebuilding the image.

---

## ✅ Project 3 - Persistent Storage

### Objective

Understand Kubernetes persistent storage.

### Concepts

- PersistentVolume (PV)
- PersistentVolumeClaim (PVC)
- Volume Mounts

### Outcome

- Created a PersistentVolume.
- Bound it to a PersistentVolumeClaim.
- Mounted persistent storage into the application.
- Learned the PV → PVC → Pod relationship.

---

## ✅ Project 4 - Kubernetes Secrets

### Objective

Manage sensitive configuration securely.

### Concepts

- Secrets
- Environment Variables
- Secret References

### Outcome

- Created Kubernetes Secrets.
- Injected credentials into the application.
- Learned secure configuration management.

> **Note:** Placeholder values are used in this repository. Replace them with your own credentials before deployment.

---

## ✅ Project 5 - Helm

### Objective

Package Kubernetes manifests into reusable Helm charts.

### Concepts

- Helm Charts
- Templates
- values.yaml
- Chart.yaml
- Helm Install
- Helm Upgrade
- Helm Rollback

### Outcome

- Converted Kubernetes manifests into a reusable Helm chart.
- Parameterized deployments using `values.yaml`.
- Managed application lifecycle using Helm.
- Learned Helm release management.

---

## ✅ Project 6 - GitOps with Argo CD

### Objective

Deploy applications directly from GitHub using GitOps principles.

### Concepts

- GitOps
- Argo CD
- Continuous Reconciliation
- Drift Detection
- Manual Synchronization
- Helm Integration

### Outcome

- Installed Argo CD on Minikube.
- Connected Argo CD to the GitHub repository.
- Deployed the Helm chart through Argo CD.
- Configured manual synchronization to understand the GitOps workflow.
- Learned how Kubernetes continuously reconciles desired state from Git.

---

# ⚙️ Deployment Workflow

```
Developer
    │
    ▼
Git Commit
    │
Git Push
    │
    ▼
GitHub Repository
    │
    ▼
Argo CD
    │
(Manual Sync)
    │
    ▼
Helm Chart
    │
    ▼
Kubernetes Cluster
    │
    ▼
NGINX Application
```

---

# 📚 Key Learnings

- Kubernetes Architecture
- Deployments & ReplicaSets
- Services & Ingress
- ConfigMaps
- Persistent Storage
- Secrets
- Helm Packaging
- Helm Release Management
- GitOps
- Argo CD
- Infrastructure as Code
- Kubernetes Troubleshooting

---

# 🚧 Upcoming Projects

- ⏳ RBAC
- ⏳ Network Policies
- ⏳ Horizontal Pod Autoscaler (HPA)
- ⏳ Prometheus
- ⏳ Grafana
- ⏳ Loki + Fluent Bit
- ⏳ Cert Manager
- ⏳ GitHub Actions
- ⏳ Production-grade Kubernetes Application

---

# 💡 About This Repository

This repository documents my journey in learning Kubernetes, Platform Engineering and Site Reliability Engineering (SRE).

Each project focuses on solving a practical problem while following production-oriented engineering practices such as GitOps, Infrastructure as Code and declarative deployments.