# Namespace

1. Following are the three namespaces are created 
- default
- kube-system
- kube-public

2. Different namespaces for the environment can be created ( such as dev, prod), quota can be allocated.Quota can be created vy YAML configiration.

3. Pod can connect to another pod using service name ( example- webserver can to DB application by name db-service)

4. Pod can also connect to the service name of another namespace in  the following format ( webserver can connect to the database - <servicename>.<namespacename>.svc.cluster (db-service.dev.svc.cluster.local)

5. cluster.local is default domain of the cluster and svc is the subdomain.

6. Executing kubectl in specific namespae

~~~bash

$ kubectl get pods --namespace=kube-system

$ kubectl create -f pod-definition.yml --namespace=dev
# namespace can also be added in definition file by specifying in metadata

$ kubectl create -f namespace-dev.yml

$ kubectl create namespace dev

# to set the namespace

$ kubectl config set-context $(kubectl config current-context) --namespace=dev

$ kubectl get pods --all-namespaces
