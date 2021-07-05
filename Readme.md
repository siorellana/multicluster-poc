# Multicluster Deploy POC

In this repositories you will find the manifest used to make a POC of multicluster deployment using Argo Cd Multicluster Features.

```tree
.
├── Readme.md
├── app01
│   ├── 00-namespace.yaml
│   ├── 01-deployment.yaml
│   └── 02-service.yaml
├── app02
│   ├── 00-namespace.yaml
│   ├── 01-deployment.yaml
│   └── 02-service.yaml
└── argocd
    ├── Readme.md
    ├── argocd-application-controller
    │   ├── clusterrole.yaml
    │   ├── clusterrolebinding.yaml
    │   ├── deployment.yaml
    │   ├── role.yaml
    │   ├── rolebinding.yaml
    │   ├── service.yaml
    │   └── serviceaccount.yaml
    ├── argocd-configs
    │   ├── argocd-cm.yaml
    │   ├── argocd-rbac-cm.yaml
    │   ├── argocd-secret.yaml
    │   ├── argocd-ssh-known-hosts-cm.yaml
    │   └── argocd-tls-certs-cm.yaml
    ├── argocd-repo-server
    │   ├── deployment.yaml
    │   └── service.yaml
    ├── argocd-server
    │   ├── clusterrole.yaml
    │   ├── clusterrolebinding.yaml
    │   ├── deployment.yaml
    │   ├── role.yaml
    │   ├── rolebinding.yaml
    │   ├── service.yaml
    │   └── serviceaccount.yaml
    ├── dex
    │   ├── deployment.yaml
    │   ├── role.yaml
    │   ├── rolebinding.yaml
    │   ├── service.yaml
    │   └── serviceaccount.yaml
    └── redis
        ├── deployment.yaml
        └── service.yaml

9 directories, 36 files
```
