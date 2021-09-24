# argo-app-of-apps
test repo for App of Apps

1. create app-proj `kubectl apply -f app-project.yaml`
2. change secret and create secret to clone repo `kubectl apply -f proj-secret.yaml`
3. run 

```
argocd app create apps \
    --dest-namespace argocd \
    --dest-server https://kubernetes.default.svc \
    --repo https://github.com/InsomniaCoder/argo-app-of-apps.git \
    --path apps  

argocd app sync apps
```