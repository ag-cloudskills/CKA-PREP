# Kube proxy

1. In kubernetes ip of the pod keeps changing and therefore services are used to access the different componts such as ( webserver, Database server). An ip is also gets assigned to the service.
2. Service is not part of pod network as it is virtual component.
3. Kubeproxy is a process in each nodes of kubernetes cluster and its job is to discover new services and every time a new service is created and it creates appropriate rule on each node to forward traffic to back end pods.one way to do it is by creating iptables rules.
4. kubeadm installs it as pod