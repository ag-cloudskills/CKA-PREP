# Replication controller & ReplicaSets

- replication controller can also be used in a single pod deployment
- replication controller can spans across the worker nodes and can increase the pods as per demand
- replication controller helps in attaining high availability/loadbalancing/scaling. It spans across the nodes.
- replication controller( legacy) and replica set( new technology) are different.
- Refer to rc-definition.yml for the definition of replication controller
- Refer to the replicaset-definition.yml for definition of replicaset.
- selector definition contains labels which can be sed to identify already running pods ( pods which are not created as part of
  replica set)
- labels is used for labelling the containers and selector can be used to identify the already running containers
- replicaset monitors the pods using label for filtering the pods
- scale command can also be used to scale out the pods
- yaml is not updated when scaling is done through cli


~~~bash
$ kubectl create -f replicaset-definition.yaml
$ kubectl get replicaset
$ kubectl delete replicaset <replciasetname>

# after making change in definition file
$ kubectl replace -f replicaset-definition.yaml
$ kubectl scale --replicas=6 -f replicaset-definition.yaml
$ kubectl scale rs new-replica-set --replicas=5
~~~