# etcd

- distributed  and reliable key value store

## etcd installation

~~~bash

export RELEASE=$(curl -s https://api.github.com/repos/etcd-io/etcd/releases/latest|grep tag_name | cut -d '"' -f 4)
wget https://github.com/etcd-io/etcd/releases/download/${RELEASE}/etcd-${RELEASE}-linux-amd64.tar.gz
# version can change as per download
tar -xvf etcd-v3.4.20-linux-amd64.tar.gz
cd etcd-v3.4.20-linux-amd64
sudo mv etcd etcdctl /usr/local/bin/
 etcd --version
~~~

## etcd in Kubernetes

- information regarding nodes, pods, configs, secrets, accounts, roles,, binding (kubctl get data from etcd)
- etcd is set up differently based on the kubernetes  deployment (kubeadm or build from scratch)
- etcd is configured as service on the master node ( build from scratch)
- default port of etcd is 2379 and url is https://<internalip>:2379
- in kubeadm method etcd is run as a pod in kube-system namespace,while when it is built from scratch etcd binary is installed and setup independently
- get commands fetch data from etcd ( eg- Nodes, PODS, configs , secrets information)
- In HA , etcd is set up in each master node
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