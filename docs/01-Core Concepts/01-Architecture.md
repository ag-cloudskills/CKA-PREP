# Architecture

MASTER node - Manage , plane , schedule, monitor nodes
ETCD CLuster -information about the nodes in higly available keystore.
Kube-Scheduler - responsible for deploying container based on the policy
Node Controller - handling nodes, onboarding of nodes
Replication controller -  desirrs number od onctainers are runing 
kube-apiserevr - managment component and orchestrates within cluster
container runtime engine - docker, rocker
kubelet - engine in each node of cluster 
kube-proxy - allow nodes to comunicated each other 