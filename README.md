# DevOps Lab 2 — Containerization & Kubernetes Orchestration

Suyash Sahu — Roll No. 2301010476 — K R Mangalam University

## Task 1: Deploy an application to Kubernetes (Minikube)
- `k8s/deployment.yaml` — Deployment running 3 replicas of nginx
- `k8s/service.yaml` — NodePort Service exposing the app on port 30080
- `.github/workflows/k8s-deploy.yml` — starts a Minikube cluster, applies the manifests and verifies the running pods
