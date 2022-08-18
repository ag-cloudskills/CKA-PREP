# Kubelet

- kubelet registers the node with the kubernetes cluster.
- when the scheduler sent the request to create the pod via apiserver, kubelet requests the container runtime environment to pull 
  the required image and run instance under the pod
- it monitors the node and pod and reports it back to the apiserver.
- Kubeadm does not automatically deploy the kubelets, it needs to be manually installed on the worker node


~~~bash

ps -aux | grep kubelet
