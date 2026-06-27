# Project 1 - Deploying Nginx on Kubernetes

## Objective

The goal of this project is to understand the fundamental building blocks of Kubernetes by deploying a simple Nginx application on a local Kubernetes cluster using Minikube.

This project demonstrates how Kubernetes Deployments, Services, and Ingress work together to expose an application.

---

## Environment

* Kubernetes (Minikube)
* Docker Driver
* macOS
* kubectl
* Nginx

---

## Kubernetes Resources

### Namespace

A dedicated namespace (`homelab`) is created to isolate all application resources from the default namespace.

---

### Deployment

The Nginx Deployment:

* Creates multiple replicas of the Nginx Pod.
* Automatically recreates Pods if they fail.
* Supports rolling updates for future application changes.

---

### Service

A Kubernetes Service is created to provide a stable endpoint for the Nginx Pods.

Initially, the Service is configured as a **ClusterIP**, allowing communication only from within the Kubernetes cluster.

---

### Ingress

An NGINX Ingress Controller is enabled in Minikube.

An Ingress resource routes HTTP requests for the hostname `nginx.local` to the Nginx Service.

This demonstrates hostname-based routing within Kubernetes.

---

## Architecture

```text
                   Client
                      │
                  Ingress
                      │
                  Service
                      │
          ┌───────────┴───────────┐
          │                       │
      Nginx Pod              Nginx Pod
```

---

## Learning Outcomes

* Creating Kubernetes namespaces
* Deploying applications using Deployments
* Scaling applications using replicas
* Exposing applications using Services
* Understanding ClusterIP networking
* Configuring an Ingress Controller
* Creating Ingress resources
* Troubleshooting Kubernetes networking in a local Minikube environment

---

## Repository Structure

```text
nginx/
├── deployment.yaml
├── service.yaml
└── ingress.yaml
```

---

## Verification

The deployment can be verified using:

```bash
kubectl get pods -n homelab
kubectl get svc -n homelab
kubectl get ingress -n homelab
```

The application can be accessed locally using:

```bash
kubectl port-forward svc/nginx 8080:80 -n homelab
```

or

```bash
minikube service nginx -n homelab --url
```

---

## Key Takeaways

This project introduced the core Kubernetes networking flow:

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

Understanding this flow is fundamental before moving on to configuration management, persistent storage, monitoring, and GitOps.
