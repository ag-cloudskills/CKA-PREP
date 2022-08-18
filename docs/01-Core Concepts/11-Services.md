# Services

- services enable the communication between internal and external applications and it enables loose coupling in micro services architecture.

- nodeport - map the node port to pod port..Valid range of port for node is 30000 - 32767. Service will also have its own ip.Only 
  mandatory value in definition is targetport.

- three ports - pod port , service port  and node port ( eg - Nodeport(30008) -> Service port(80)-> pod port (80))

- clusterip - virtual ip inside cluster to  enable communication between different services (frontend server to backend server)

- loadbalancer - it provisions LB in supported cloud providers

~~~bash
# to create service

$ kubectl create -f <nameofyaml>
$ kubetcl get svc
~~~

- service is created in same format irrespective of deployment (one pod-one node, multiple pods-one node, one pod - multiple pod)
- service uses following configuration for the HA:
    Algorithim: Random
    SessionAffinity: Yes