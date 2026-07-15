# Kubernetes Homelab 🚀

A hands-on Kubernetes Homelab built on **Minikube** to learn Kubernetes administration, Helm, storage, networking, and platform engineering concepts.

The goal of this repository is to build production-oriented Kubernetes skills by implementing one project at a time while following infrastructure-as-code and GitOps principles.

---

## 🛠️ Environment

* Kubernetes (Minikube)
* Docker Desktop
* kubectl
* Helm
* VS Codium
* Git & GitHub
* NGINX

---

# 📚 Projects

## ✅ Project 1 – NGINX Deployment, Service & Ingress

### Objective

Deploy a simple NGINX application and expose it using Kubernetes networking.

### Concepts Covered

* Deployments
* ReplicaSets
* Services
* NodePort
* ClusterIP
* Ingress
* Labels & Selectors
* Namespace Management

### Outcome

* Deployed an NGINX application with multiple replicas.
* Exposed the application using both Service and Ingress.
* Configured local hostname (`nginx.local`) for browser access.
* Learned Kubernetes networking fundamentals.

---

## ✅ Project 2 – ConfigMaps

### Objective

Externalize application configuration using ConfigMaps.

### Concepts Covered

* ConfigMaps
* Volume Mounts
* Configuration Management

### Outcome

* Created a ConfigMap containing a custom `index.html`.
* Mounted the ConfigMap into the NGINX container.
* Updated the application without rebuilding the container image.

---

## ✅ Project 3 – Persistent Storage

### Objective

Understand Kubernetes persistent storage.

### Concepts Covered

* PersistentVolume (PV)
* PersistentVolumeClaim (PVC)
* Volume Mounts
* Persistent Storage

### Outcome

* Created a PersistentVolume and PersistentVolumeClaim.
* Mounted persistent storage into the NGINX container.
* Learned the relationship between Pods, PVCs and PVs.

---

## ✅ Project 4 – Kubernetes Secrets

### Objective

Securely inject sensitive information into applications.

### Concepts Covered

* Secrets
* Environment Variables
* Secret References

### Outcome

* Created Kubernetes Secrets.
* Injected secret values into the application as environment variables.
* Learned how applications securely consume credentials.

> **Note:** Placeholder values are used in this repository. Replace them with your own values before deploying.

---

## ✅ Project 5 – Helm

### Objective

Package Kubernetes manifests into a reusable Helm chart.

### Concepts Covered

* Helm Charts
* Chart.yaml
* values.yaml
* Templates
* Helm Install
* Helm Upgrade
* Helm Rollback
* Helm Release Management

### Outcome

* Converted manually created Kubernetes manifests into a Helm chart.
* Parameterized deployments using `values.yaml`.
* Successfully deployed the application with Helm.
* Managed application upgrades through Helm releases.
* Learned how Helm templates render into standard Kubernetes manifests.

---

# 📂 Repository Structure

```text
.
├── project1-basic-nginx/
├── project2-configmap/
├── project3-persistent-storage/
├── project4-secrets/
├── project5-helm/
├── README.md
```

---

# 🚀 Running the Projects

### Clone the repository

```bash
git clone https://github.com/<your-github-username>/kubernetes-homelab.git

cd kubernetes-homelab
```

### Start Minikube

```bash
minikube start
```

### Enable Ingress

```bash
minikube addons enable ingress
```

### Deploy with kubectl (Projects 1–4)

```bash
kubectl apply -f .
```

### Deploy with Helm (Project 5)

```bash
helm install my-nginx ./project5-helm/nginx \
  -n homelab \
  --create-namespace
```

Upgrade after modifying `values.yaml`:

```bash
helm upgrade my-nginx ./project5-helm/nginx -n homelab
```

View release history:

```bash
helm history my-nginx -n homelab
```

Rollback if needed:

```bash
helm rollback my-nginx <revision> -n homelab
```

---

# 📖 Key Learnings

* Kubernetes object lifecycle
* Declarative infrastructure
* Application networking
* Persistent storage
* Configuration management
* Secret management
* Helm templating
* Helm release management
* Kubernetes troubleshooting
* Infrastructure as Code (IaC)

---

# 🎯 Upcoming Projects

* ⏳ Project 6 – Kubernetes Monitoring (Prometheus & Grafana)
* ⏳ Project 7 – Horizontal Pod Autoscaler (HPA)
* ⏳ Project 8 – RBAC
* ⏳ Project 9 – Network Policies
* ⏳ Project 10 – Argo CD (GitOps)
* ⏳ Project 11 – GitHub Actions CI/CD
* ⏳ Project 12 – Loki + Fluent Bit Logging
* ⏳ Project 13 – Cert Manager & TLS
* ⏳ Project 14 – Production-ready Kubernetes Application

---

## ⭐ About This Repository

This repository is part of my continuous learning journey in Kubernetes, Platform Engineering and Site Reliability Engineering (SRE). Each project focuses on solving a real operational problem while following production-oriented Kubernetes practices.
