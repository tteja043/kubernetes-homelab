# Kubernetes Homelab - Nginx Deployment

This project is a simple Kubernetes homelab setup running on Minikube (Docker driver) on macOS. The goal is to learn and practice core Kubernetes concepts by deploying and exposing an Nginx application.

## Components Used

* **Minikube** - Local Kubernetes cluster for development and learning.
* **Docker Driver** - Used by Minikube to run the Kubernetes node.
* **kubectl** - Kubernetes command-line tool for cluster management.
* **Nginx** - Sample web application deployed in the cluster.
* **Deployment** - Manages Nginx Pods and ensures desired replica count.
* **Service (ClusterIP)** - Provides stable internal networking and load balancing across Nginx Pods.
* **Ingress Controller (NGINX Ingress)** - Handles external HTTP routing into the cluster.
* **Ingress Resource** - Routes traffic for the hostname `nginx.local` to the Nginx Service.

## Architecture

User → Ingress → Service → Nginx Pods

1. Nginx is deployed using a Kubernetes Deployment with multiple replicas.
2. A ClusterIP Service exposes the Pods internally within the cluster.
3. An Ingress resource maps the hostname `nginx.local` to the Nginx Service.
4. The NGINX Ingress Controller processes incoming requests and forwards them to the appropriate backend Pods.

## Learning Outcomes

* Creating and managing Kubernetes Namespaces
* Deploying applications using Deployments
* Exposing applications using Services
* Configuring and troubleshooting Ingress
* Understanding Kubernetes networking and service discovery
* Working with Minikube in a local development environment
* Troubleshooting networking issues specific to Minikube and Docker on macOS
