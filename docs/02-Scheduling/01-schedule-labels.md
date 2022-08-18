# Manual Scheduling

- role of schedule to select the node for the pod
- If the nodeName field is not present in manifest file , then the pod is candidate for scheduling
- It can be done by mentioning the parameter nodeName in yaml file
- nodeName filed can't be changed for running node
- node for the pod can be changed by using pod-bind definition and then convert the binding in Json. Once the conversion is done, 
  api requests need to be fired.

# Labels,Selector and Annotations

- labels are used for identifying the objects such as pods, replicasets
- Selector is used to identify the objects by filtering the labels
- Annotations are used to define the additional information such as buid version, contact details

~~~bash
$ kubectl get pods --selector <lablekey>=<labelvalue>
$ kubectl get pods --selector env=prod,bu=finance,tier=frontend