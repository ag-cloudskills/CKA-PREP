# PODS

- POD is the smallest component of cluster
- Pods generally have one to one relationship with container(additional containers are not added in same pod for scaling)
- Helper container can be setup in same pod.
- to deploy pods

~~~bash
# create pods
$ kubectl run nginx --image nginx
# check status pods
$ kubectl get pods
# to describe pods
$ kubectl describe pod <podname>
# to check where pods are deployed
$ kubectl get pods -o wide
# to create pod via cli and deployment file
$ kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml
# to edit image
$ kubectl edit pod <podname>
# if yaml file is edited
# kubectl apply -f redis-definition.yaml 