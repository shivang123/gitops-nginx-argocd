# GitOps with Argo CD and Gitea (NGINX Demo)

This project demonstrates a complete GitOps workflow using **Argo CD** and **Gitea** to deploy and manage an NGINX application on Kubernetes.

## Tech Stack
- Kubernetes
- Argo CD
- Gitea (self-hosted Git)
- GitHub (project showcase)
- NGINX

## Architecture
Git (Gitea/GitHub) → Argo CD → Kubernetes

## Project Structure
gitops-nginx-argocd/
├── app/
│   ├── deployment.yaml
│   └── service.yaml
├── argocd/
│   └── application.yaml
├── screenshots/
│   ├── argocd-app.png
│   ├── argocd-sync.png
│   └── nginx-pods.png
└── README.md

## What This Project Demonstrates
- GitOps-based application deployment
- Automated sync and self-healing in Argo CD
- Declarative Kubernetes configuration
- Handling self-signed TLS certificates in Git servers

---

## GitOps Workflow
1. Application manifests are stored in Git
2. Argo CD continuously monitors the repository
3. Any Git commit automatically reconciles the cluster state
4. Manual changes are reverted (self-healing)

---

## GitOps Proof: Scaling via Git
Scaling NGINX from 2 to 3 replicas was done **only via Git commit**.

```yaml
replicas: 3

