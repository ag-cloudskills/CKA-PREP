# etcd

- etcd is configured on the master node
- get commands fetch data from etcd ( eg- Nodes, PODS, configs , secrets information)
- etcd is set up diffeetly based on the kubernetes  deployment ( kubeadm or build from scratch)
- In kubeadm etcd is run as a pod in kube-system namespace,while when it is built from scratch etcd binary is installed and setup independetly
- default port of etcd is 2379 and url is https://<internalip>:2379
- In HA , etcd is ste up in each master node
- Set up the etcd api version

~~~bash
export ETCDCTL_API=3
# if version is not set , then the default value is 2
# version 3 commands

etcdctl snapshot save
etcdctl enspoint health
etcdctl get
etcdctl put

# version 2 commands

etcdctl backup
etcdctl cluster-health
etcdctl mk  # creates new key
etcdctl mkdir
etcdctl set