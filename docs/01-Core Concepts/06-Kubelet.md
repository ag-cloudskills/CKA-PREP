# Kubelet

1. Kubelet registers the node with the kubernetes cluster.
2. When the scheduler sent teh request to create the pod via apiserver, kubelet requests the container runtime environment to pull the required image and run instance under the pod
3. It monitors the node and pod and report it back to the apiserver.
4. Kubeadm does not automatically deploy the kubelets, it needs to be manually installed