# Imperative vs Declarative

1. Imperative - Step wise instructions ( kubectl run, create, edit, expose commands)
2. Declarative - kubectl apply commands

~~~bash

$ kubectl expose pod redis --port=6379 --name redis-service

 kubectl run custom-nginx --image nginx --dry-run=client --port=8080  -o yaml >nginx.yaml

 kubectl create deployment redis-deploy --image redis --namespace=dev-ns --dry-run=client -o yaml > deploy.yaml
