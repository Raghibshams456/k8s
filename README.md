# Kubernetes Quick Start Guide

This repository provides a simple way to create a Kubernetes cluster locally using Minikube, and deploy a scalable application using the included manifest.

---

## 1. Create a Cluster

**Option A — Quick Start (Minikube, Local):**
```sh
minikube start --driver=docker
minikube addons enable ingress
```

---

## 2. Deploy Manifests

Apply the combined manifest file included in this repository:

```sh
kubectl apply -f scalable_app.yaml
```

---

### About `scalable_app.yaml`

This manifest includes:
- **Namespace:** `navatech`
- **Deployment:** `sample-app`
  - 3 replicas
  - Resource requests/limits
  - Readiness and liveness probes
  - Affinity rules
- **Service:** `sample-app-svc` (ClusterIP)

You can find the full YAML in this repository as [`scalable_app.yaml`](./scalable_app.yaml).

---
