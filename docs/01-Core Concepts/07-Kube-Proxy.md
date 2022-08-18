# Kube proxy

- in kubernetes ip of the pod keeps changing and therefore services are used to access the different components such as ( 
  webserver, Database server). An ip is also gets assigned to the service.
- Service is not part of pod network as it is virtual component.
- kubeproxy is a process in each nodes of kubernetes cluster and its job is to discover new services and every time a new service 
  is created and it creates appropriate rule on each node to forward traffic to back end pods.One of the way it is configured by creating iptables rules.
- kubeadm installs it as pod
- it is deployed as demonset