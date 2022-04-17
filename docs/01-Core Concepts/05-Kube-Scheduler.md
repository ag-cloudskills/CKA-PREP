# Kube Scheduler

1. Function of scheduler is to determine the nodes on which pod needs to run.
2. It does the decision making on the following way:
    - Filter the nodes which are straight away not eligible( based on the criterion such as cpu, memory)
    - Rank the nodes based on the available resources and then select the node

*Scheduler does not deploy the container*

3.To view the scheduler configuration
~~~bash
# kubeadm
$ cat /etc/kubernetes/manifest/kube-scheduler.yaml

# withoutkubeadm
$ cat /etc/systemd/system/kube-scheduler.service
