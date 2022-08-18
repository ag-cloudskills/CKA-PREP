# kube controller manager

- watch status of the each component of the system and take necessary actions to remediate the situation.
- node controller checks status of nodes every 5 seconds(node monitor period) via kube-apiserver. If the heartbeat is not 
  recovered , then node is marked as unreachable( node monitor grace period - 40s). If the node remains unhealthy for 5 mins ( POD eviction timeout) , then pod is created in healthy node( given the pods are part of the replica set).
- replication controller- monitoring the status of replica set and ensure the number of modes are always present as defined.
- example of controller are - Deployment, namespace, endpoint, job.etc.
- to view kube controller configuration

~~~bash
# via kubeadm
$ kubectl get pods -n kube-system
$ cat /etc/kubernetes/manifest/kube-controller-manager.yaml

# non kubeadm setup
$ cat /etc/systemd/system/kube-controller.service

# Checking process
ps -aux | grep kube-controller-manager