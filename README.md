# 🚀 DevSecOps Tetris Manifest Repository

This repository contains the Kubernetes deployment and service manifests for the Tetris application.

The repository is used as part of a GitOps workflow where Jenkins automatically updates the container image version and ArgoCD synchronizes the changes to the Amazon EKS cluster.

---

## 🎯 Repository Purpose

This repository serves as the **GitOps source of truth** for Kubernetes deployments.

Instead of deploying directly to the cluster, Jenkins updates the Kubernetes manifest with the latest Docker image version. ArgoCD continuously monitors this repository and automatically synchronizes any changes to the Amazon EKS cluster.

This approach provides:

* Automated deployments through GitOps
* Version-controlled Kubernetes manifests
* Improved deployment traceability
* Faster rollback capabilities
* Consistent cluster state management

---

## ☸️ Kubernetes Resources

### Deployment

The deployment manifest defines:

* Application: Tetris
* Replicas: 3
* Container Image: Docker Hub
* Container Port: 3000

### Service

The service manifest defines:

* Service Type: LoadBalancer
* External Port: 80
* Target Port: 3000

---

## 🔄 GitOps Workflow

```text
Application Repository
          │
          ▼
       Jenkins
          │
          ▼
Update deployment.yml
          │
          ▼
GitHub Manifest Repository
          │
          ▼
        ArgoCD
          │
          ▼
Amazon EKS Cluster
          │
          ▼
Tetris Application
```

---

## 🚀 Deployment

Apply the manifest manually:

```bash
kubectl apply -f deployment.yml
```

Verify resources:

```bash
kubectl get all
```
