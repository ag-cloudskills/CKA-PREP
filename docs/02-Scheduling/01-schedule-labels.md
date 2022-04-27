# Manual Scheduling

 It can be done by mentioning the parameter nodeName in yaml file

# Labels,Selector and Annotations

- labels are used for identifying the objects such as pods, replicasets
- Selector is used to identify the objects by filtering the labels
- Annotations are used to define the additional information such as buid version, contact details

~~~bash
$ kubectl get pods --selector <lablekey>=<labelvalue>
$ kubectl get pods --selector env=prod,bu=finance,tier=frontend