# Replication controller & ReplicaSets

1. Replication controller helps in attaining high availability/loadbalancing/scaling. It spans across the nodes.
2. Replication controller( legacy) and replica set( new technology) are different.
3. Refer to rc-definition.yml for the definition of replication controller
4. Refer to the replicaset-definition.yml for definition of replicaset.
5. Labels is used for labelling the containers and selector can be used to identify the already running containers

~~~bash
$ kubectl create -f replicaset-definition.yaml
$ kubectl get replicaset
$ kubectl delete replicaset <replciasetname>
# after making change in definition file
$ kubectl replace -f replicaset-definition.yaml
# yaml is not updated when scaling is done through cli
$ kubectl scale --replicas=6 -f replicaset-definition.yaml
$ kubectl scale rs new-replica-set --replicas=5
~~~