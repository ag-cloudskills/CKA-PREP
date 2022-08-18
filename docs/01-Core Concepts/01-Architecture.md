# Architecture

## 10 thousand feet View

- Control ships  -> Master Node
- cargo ships  ->  Worker Node
- MASTER node - Manage , plane , schedule, monitor nodes
- ETCD CLuster -It is highly available key value data store which stores the information about the nodes
- Kube-Scheduler - responsible for deploying container based on the policy, worker node capacity
- Node Controller - handling nodes, on-boarding of new nodes
- Replication controller -  desired number od containers are running
- kube-apiserevr - management component and orchestrates within cluster
- container runtime engine - docker, containerd, rocket
- kubelet - engine in each node of cluster , it receives communication from kube-apiserver
- kube-proxy - allow container on worker nodes to communicat each other

image.png <Refer to architecture pic>