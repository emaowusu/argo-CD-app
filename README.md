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

## Username and Password == admin and the base64 decoded
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
```
## Decode the Password
```bash
echo PASSWORD | base64 --decode
```



