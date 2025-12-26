# GitOps NGINX Project – Key Learnings

This file summarizes what I learned while building a GitOps demo using **Argo CD** and **Gitea**.

## 1. GitOps Principles
- Git is the **single source of truth** for application state.
- Changes to the cluster should only come from **Git commits**.
- Argo CD continuously reconciles the cluster to match Git.

## 2. Kubernetes Best Practices
- Always use **namespaces** for isolation (`gitops-demo` used here).
- Use **Deployment + Service** for app abstraction.
- Avoid invalid fields in manifests (e.g., `replicas` under containers).

## 3. Argo CD Features
- Automated sync keeps cluster in sync with Git.
- Self-healing automatically fixes manual changes.
- UI provides resource tree, history, and health status.
- Sync options like `CreateNamespace=true` help auto-create namespaces.

## 4. Git & GitHub Skills
- Proper branch naming (`main`) is important for modern GitOps.
- Commit messages should clearly explain the change.
- Using multiple remotes (Gitea + GitHub) is possible.

## 5. Practical Demo Skills
- Scaling replicas **only via Git** proves GitOps workflow.
- Self-healing demo: manually scaling pods triggers automatic reconciliation.
- Shows how declarative infrastructure works in practice.

## 6. Next Steps / Future Enhancements
- Add **Kustomize overlays** for dev/prod environments.
- Replace raw YAML with **Helm charts** for modular apps.
- Demonstrate **rollback** via Git commit.
- Explore **App-of-Apps pattern** for multi-service apps.

