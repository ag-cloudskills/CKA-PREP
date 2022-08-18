# taints & toleration

- taint can be used to restrict the  deployment of pods on the node. 
- toleration can be used to overcome the specific taint and will be added in the pod-definition yaml
- three taint effects
  - NoSchedule
  - PreferNoschedule
  - noExecute
- taint and toleration can't force the pod to go to the specific node.



~~~bash
# putting a taint
kubectl taint nodes <nodename> key=value:effect
kubectl taint nodes node01 spray=mortein:NoSchedule
#untaint the node
kubectl taint nodes node01 spray=mortein:NoSchedule

# Check taint on the master node

kubectl describe node kubemaster | grep Taint
