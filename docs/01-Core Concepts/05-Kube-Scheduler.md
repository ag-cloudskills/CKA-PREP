# Kube Scheduler

- function of scheduler is to determine the nodes on which pod needs to run. ( kubelet creates the  pod)
- it does the decision making on the following way:
- filter the nodes which are straight away not eligible( based on the criterion such as cpu, memory)
- rank (1-10) the nodes based on the available resources and then select the node

*Scheduler does not deploy the container*

- To view the scheduler configuration

~~~bash
# kubeadm
$ cat /etc/kubernetes/manifest/kube-scheduler.yaml

# withoutkubeadm

cat /etc/systemd/system/kube-scheduler.service

ps -aux | grep kube-scheduler
