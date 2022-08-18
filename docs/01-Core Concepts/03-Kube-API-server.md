# Kube-api Server

- Kubeapi authenticates user and validate the request, and retrieves the data from etcd cluster

- POD creation request workflow
  - kube-api server authenticate the user
  - validate the request
  - retrieves the data from etcd cluster
  - creates pod object(without assigned node)
  - updates etcd that new pod is created
  - update the user pod is created
  - scheduler continuously monitors the apiserver and gets the information new pod is created without node
  - scheduler identifies the right node and communicate this information to api server
  - api server updates this information to etcd and pass this information to kubelet of right worker node
  - kubelet creates pod on worker node and instructs the container runtime engine to deploy the application image
  - once the pod is successfully created,kubelet communicates the information to api server which updates the information to etcd 
    cluster

* Kubeapi is the only component which can communicates with etcd directly*

- Certificates are used for the authentication

- To view api- server configuration

~~~bash
# in kubeadm system
kubectl get pods -n kubesystem
cat /etc/kubernetes/manifests/kube-apiserver.yaml

# in normal( non-kubeadm) setup
cat /etc/systemd/system/kube-apiserver.service

# Checking process
ps -aux | grep kube-apiserver