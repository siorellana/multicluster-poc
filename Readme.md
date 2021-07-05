# Multicluster Deploy POC

In this repositories you will find the manifest used to make a POC of multicluster deployment using Argo Cd Multicluster Features.

```tree
.
├── Readme.md
├── app01
│   ├── 00-namespace.yaml
│   ├── 01-deployment.yaml
│   ├── 02-service.yaml
│   └── kustomization.yaml
├── app02
│   ├── 00-namespace.yaml
│   ├── 01-deployment.yaml
│   ├── 02-service.yaml
│   └── kustomization.yaml
├── app03
│   ├── 00-namespace.yaml
│   ├── 01-deployment.yaml
│   ├── 02-service.yaml
│   └── kustomization.yaml
├── argocd
│   ├── Readme.md
│   ├── argocd-application-controller
│   │   ├── clusterrole.yaml
│   │   ├── clusterrolebinding.yaml
│   │   ├── deployment.yaml
│   │   ├── role.yaml
│   │   ├── rolebinding.yaml
│   │   ├── service.yaml
│   │   └── serviceaccount.yaml
│   ├── argocd-configs
│   │   ├── argocd-cm.yaml
│   │   ├── argocd-rbac-cm.yaml
│   │   ├── argocd-secret.yaml
│   │   ├── argocd-ssh-known-hosts-cm.yaml
│   │   └── argocd-tls-certs-cm.yaml
│   ├── argocd-repo-server
│   │   ├── deployment.yaml
│   │   └── service.yaml
│   ├── argocd-server
│   │   ├── clusterrole.yaml
│   │   ├── clusterrolebinding.yaml
│   │   ├── deployment.yaml
│   │   ├── role.yaml
│   │   ├── rolebinding.yaml
│   │   ├── service.yaml
│   │   └── serviceaccount.yaml
│   ├── dex
│   │   ├── deployment.yaml
│   │   ├── role.yaml
│   │   ├── rolebinding.yaml
│   │   ├── service.yaml
│   │   └── serviceaccount.yaml
│   └── redis
│       ├── deployment.yaml
│       └── service.yaml
└── k3s
    ├── Readme.md
    ├── database
    │   ├── Vagrantfile
    │   ├── my.cnf
    │   ├── mysql
    │   │   ├── conf.d
    │   │   │   ├── mysql.cnf
    │   │   │   └── mysqldump.cnf
    │   │   ├── debian-start
    │   │   ├── debian.cnf
    │   │   ├── mariadb.cnf
    │   │   ├── mariadb.conf.d
    │   │   │   ├── 50-client.cnf
    │   │   │   ├── 50-mysql-clients.cnf
    │   │   │   ├── 50-mysqld_safe.cnf
    │   │   │   └── 50-server.cnf
    │   │   ├── my.cnf
    │   │   └── my.cnf.fallback
    │   └── readme.md
    ├── master1
    │   ├── Vagrantfile
    │   └── ubuntu-bionic-18.04-cloudimg-console.log
    ├── master2
    │   └── Vagrantfile
    ├── nginx.conf
    ├── worker01
    │   └── Vagrantfile
    ├── worker03
    │   └── Vagrantfile
    ├── worker04
    │   └── Vagrantfile
    └── worker05
        └── Vagrantfile

21 directories, 65 files
```
