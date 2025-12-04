# Argo-CD-app

## Create and apply argocd
```bash
kubectl create namespace argocd
```
```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Get argocd pods in watch (-w) mode
```bash
kubectl get pod -n argocd
```
```bash
kubectl get pod -n argocd -w 
```

## Get argocd Service
```bash
kubectl get svc -n argocd
```

## Port Forwarding
```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## Access ArgoCD UI
```bash
https://127.0.0.1:8080
```

## Username = admin then get the encoded password
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
```
## Decode the Password
```bash
echo theEncodedPASSWORD | base64 --decode
```

## Decode and Get the Password once
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 --decode
```
