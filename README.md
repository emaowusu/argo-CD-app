# argo-CD-app

## Create and apply argocd pod
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

## Get argocd pods in watch (-w) mode
kubectl get pod -n argocd
kubectl get pod -n argocd -w 

## Get argocd Service
kubectl get svc -n argocd

## Port Forwarding
kubectl port-forward svc/argocd-server -n argocd 8080:443

## Username and Password == admin and the base64 decoded
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
echo NDFmUzlNY0ZqdWxjVWxhbA== | base64 --decode



