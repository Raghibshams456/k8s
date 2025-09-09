1) Create cluster
Option A — Quick: minikube (local)
minikube start --driver=docker
minikube addons enable ingress

2) Deploy manifests

Apply the combined manifest file included in this repo:

kubectl apply -f scalable_app.yaml

File: scalable_app.yaml — this contains Namespace navatech, Deployment sample-app (3 replicas, resource requests/limits, readiness/liveness probes, affinity), Service sample-app-svc (ClusterIP), Ingress sample-app-ingress, PodDisruptionBudget sample-app-pdb, and HPA sample-app-hpa.

(Full YAML is included in this repository as scalable_app.yaml.)