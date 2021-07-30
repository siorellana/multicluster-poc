# ArgoCD Instalation

## Install with Helm

First at all, install Helm.

`brew install helm`

Then, add teh Argocd repository to helm

`helm repo add argo https://argoproj.github.io/argo-helm`

`helm repo update`

## Finally, install ArgoCD

```bash
helm install argo argo/argo-cd -n argocd --wait
NAME: argo
LAST DEPLOYED: Fri Jul  2 11:03:08 2021
NAMESPACE: argocd
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
In order to access the server UI you have the following options:

1. kubectl port-forward service/argo-argocd-server -n argocd 8082:443

    and then open the browser on http://localhost:8080 and accept the certificate

2. enable ingress in the values file `server.ingress.enabled` and either
      - Add the annotation for ssl passthrough: https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/ingress.md#option-1-ssl-passthrough
      - Add the `--insecure` flag to `server.extraArgs` in the values file and terminate SSL at your ingress: https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/ingress.md#option-2-multiple-ingress-objects-and-hosts


After reaching the UI the first time you can login with username: admin and the random password generated during the installation. You can find the password by running:

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

(You should delete the initial secret afterwards as suggested by the Getting Started Guide: https://github.com/argoproj/argo-cd/blob/master/docs/getting_started.md#4-login-using-the-cli)
```

## You can also export the manifest for backup or customization purposes

`
helm template argo/argo-cd --output-dir ../argocd
`

## Crear aplicaciones

argocd app create app02 --repo <https://github.com/siorellana/multicluster-poc.git> --path app02 --dest-server <https://kubernetes.default.svc> --dest-namespace app02
