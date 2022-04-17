# kube controller manager

1. Watch status of the each component of the system and take necessary actions to remediate the situation.
2. Node controller checks status of nodes every 5 seconds(node monitor period) via kube-apiserver. If the heartbeat is not recovered , then node is marked as unreachable( node monitor grace period - 40s). If the node remains unhealthy for 5 mins ( POD eviction timeout) , then pod is created in healthy node( given the pods are part of the replica set).
3. Replication controller- monitoring the status of replica set and ensure the number of modes are always present as defined.
4. Example of controller are - Deployment, namespace, endpoint, job.etc.
5. To view kube controller configuration

~~~bash
# via kubeadm
$ kubectl get pods -n kube-system
$ cat /etc/kubernetes/manifest/kube-controller-manager.yaml

# non kubeadm setup
$ cat /etc/systemd/system/kube-controller-manager.service
