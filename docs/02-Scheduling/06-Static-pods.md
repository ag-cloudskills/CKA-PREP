# Static pods

- keep the definition files in path /etc/kubernetes/manifests
- only pods can be creates in this manner and kubelet can access the above path
- no kubectl is available
- usecase is  control plane components ad static pods

~~~
ps -aux | grep kubelet
config=/var/lib/kubelet/config.yaml
staticPodPath: /etc/kubernetes/manifests
