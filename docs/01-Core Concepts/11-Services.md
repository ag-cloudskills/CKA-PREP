# Services

1. Services enable the communication between internal and external applications and it enables loose coupling in micro services architecture.

2. Nodeport - map the node port to pod port. Nodeport(30008) -> Service port(80)-> pod port (80).Valid range od port for node is 30000 - 32767. Service will also have its own ip.  only mandatory value in definition is targetport.

~~~bash
# to create service

$ kubectl create -f <nameofyaml>
$ kubetcl get svc
~~~

Service is created in same format irrespective of deployment (one pod-one node, multiple pods-one node, one pod - multiple pod)

3. ClusterIp


4. Loadbalancer 