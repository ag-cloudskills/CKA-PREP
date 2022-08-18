# Nodes Selector

- node selector is used  for the deployment of the pods on the nodes
- first it is required to label the node with keyvalue pair
- Then configure the selector to select the label
- limitations for the advanced expression

kubectl label nodes <nodename> <label-key>=<lable-value>
kubectl label nodes node01 size=medium

# Nodes affinity

- to deploy the pods on specific nodes
- different operators can be used with nodes affinity
- types of affinity
 - requiredDuringSchedulingIgnoredDuringExecution
 - preferredDuringSchedulingIgnoredDuringExecution

 Planned
 - requiredDuringSchedulingRequiredDuringExecution
 - preferredDuringSchedulingRequiredDuringExecution

 - combination of taint/toleration  and node affinity will be recommended approach 
    for the production deployment 