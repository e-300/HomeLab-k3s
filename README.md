# 🏠 Homelab Kubernetes GitOps

A production-ready GitOps setup for my K3s homelab cluster, demonstrating modern DevOps practices and cloud-native technologies.

## 🎯 Overview

This repository manages my 3-node K3s Kubernetes cluster using GitOps principles. All infrastructure and application deployments are version-controlled and automatically synced to the cluster.

## 🛠️ Tech Stack

- **Kubernetes Distribution**: K3s (lightweight Kubernetes)
- **GitOps Tool**: ArgoCD (declarative continuous deployment)
- **Secret Management**: Sealed Secrets (encrypted secrets safe for Git)
- **Environment Strategy**: Development → Staging → Production namespaces
- **Infrastructure as Code**: 100% declarative YAML manifests

## 🔐 Security

All secrets in this repository are **encrypted using Sealed Secrets**:
- ✅ Safe to commit to public Git repository
- ✅ Only decryptable by the cluster's private key (never leaves the cluster)
- ✅ Demonstrates real-world security best practices

**Note**: No plaintext secrets exist in this repository. All sensitive data is encrypted before being committed.

## 📁 Repository Structure
```
.
├── namespaces/              # Kubernetes namespace definitions
│   └── namespaces.yaml
├── secrets/                 # Sealed secrets (encrypted)
│   ├── development/
│   ├── staging/
│   └── production/
├── deployments/             # Application deployments
│   ├── development/
│   ├── staging/
│   └── production/
├── services/                # Kubernetes services
└── argocd/                  # ArgoCD application definitions
    └── applications/
```

## 🚀 Deployment Flow
```
1. Code change pushed to Git
2. ArgoCD detects changes automatically
3. Changes deployed to development namespace
4. After testing, promoted to staging
5. After validation, promoted to production
```

## 🏗️ Infrastructure

- **Cluster**: 3-node K3s cluster (HA setup)
- **Ingress**: Traefik (built-in with K3s)
- **GitOps**: ArgoCD for continuous deployment
- **Secrets**: Sealed Secrets for GitOps-friendly secret management

## 📚 What This Demonstrates

- ✅ GitOps workflow (infrastructure as code)
- ✅ Multi-environment strategy (dev/staging/prod)
- ✅ Secret management in public repositories
- ✅ Kubernetes best practices
- ✅ CI/CD with ArgoCD
- ✅ High-availability cluster setup

## 🔧 Technologies Used

![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)
![K3s](https://img.shields.io/badge/K3s-FFC61C?style=for-the-badge&logo=k3s&logoColor=black)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

## 📖 Learning Resources

This setup follows industry best practices from:
- [The Twelve-Factor App](https://12factor.net/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [GitOps Principles](https://opengitops.dev/)

## 📝 License

MIT License - Feel free to use this as a reference for your own homelab!

---

**Built with ❤️ for learning and demonstrating modern DevOps practices**
