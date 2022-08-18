# kubectl commands

## commands

~~~bash
kubectl run nginx --image nginx
kubectl get pods
kubectl get po elephant -o yaml > elephant.yaml
kubectl descibe pod <podname>
kubectl get pods -o wide
kubetcl delete pod <podname>
kubectl create -f <pod-definition.yml
kubectl apply -f pod-definition.yml ( apply after making manaual edit)
kubectl edit pod redis ( in real time)
kubectl replace --force -f <filename>
# to list replicationcontroller
kubectl get replicationcontroller

kubectl get events
~~~

## Replicaset commands
~~~bash
# to create replicaset
kubectl create -f replicaset-definition.yaml
# to list replicaset
kubectl get replicaset
# find detail on replciaset
kubectl describe replicasetls
# to delete replicaset
kubectl delete replicaset <replciasetname>
# to scale replicaseset
# edit the file
kubectl edit rs <rsname>>
kubectl replace -f replicaset-definition.yml
# scale directly from cli
kubectl scale --replicas=6 -f replicaset-definition.yml
# by using the name under metadata
kubectl scale --replicas=6 replicaset <replicasetname>
# using selector to select pods
kubectl get pods --selector app=App1

~~~

## Deployment commands

~~~bash

# to create deployments
kubectl create deployment blue --image=nginx --replicas=3
kubectl create -f deployment-definition.yaml

# to list deployment
kubectl get deployments
# to list everything
kubectl get all


## Services

~~~bash
kubetcl get svc
kubectl describe svc <svcname>

## namesapce

kubectl get namespaces
kubectl create -f <namespace-definition.yaml>
kubectl create namespace dev
kubectl get pods --namespace=<namespacename>

## switch namespace

kubectl config set-context $(kubectl config current-context) --namespace=<namespacename>
kubectl get pods # without giving namespace
kubectl get pods --all namespaces

## Scheduler

kubectl get pods  --namespace=kube-system


## taint

kubectl taint nodes <nodename> key=value:effect
kubectl describe node kubemaster | grep Taint

## Daemonset

kubectl get daemonsets

kubectl describe daemonsets monitoring-daemon
kubectl get ds --all-namespaces
kubectl describe ds kube-flannel-ds --namespace=kube-system | grep Image