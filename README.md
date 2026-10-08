# DevOps Lab 2 — Containerization & Kubernetes Orchestration

Suyash Sahu — Roll No. 2301010476 — K R Mangalam University

## Task 1: Deploy an application to Kubernetes (Minikube)
- `k8s/deployment.yaml` — Deployment running 3 replicas of nginx
- `k8s/service.yaml` — NodePort Service exposing the app on port 30080
- `.github/workflows/k8s-deploy.yml` — starts a Minikube cluster, applies the manifests and verifies the running pods

## Task 2: Rolling updates, rollbacks and scaling
- `k8s/strategy/deployment.yaml` — Deployment with a RollingUpdate strategy (maxSurge 1, maxUnavailable 1)
- `k8s/strategy/service.yaml` — NodePort Service on port 30081
- `.github/workflows/k8s-strategies.yml` — rolling update v1→v2, faulty v3 + rollback, rollback to revision 1, scaling 4→8→2

## Task 3: Containerization & orchestration report
- `app/` — Python web app and its `Dockerfile` (non-root user, health check)
- `k8s/app/` — Deployment (zero-downtime rolling update), NodePort Service (30082) and HorizontalPodAutoscaler (2–8 pods at 50% CPU)
- `.github/workflows/k8s-report.yml` — builds the image inside Minikube, deploys, rolls out v2.0, scales manually and autoscales under load
