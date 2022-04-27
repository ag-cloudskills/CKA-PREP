# taints & toleration

~~~bash
# putting a taint
kubectl taint nodes <nodename> key=value:effect
kubectl taint nodes node01 spray=mortein:NoSchedule
#untaint the node
kubectl taint nodes node01 spray=mortein:NoSchedule-