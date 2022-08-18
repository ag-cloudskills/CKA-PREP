# Resource limits

- CPU( 0.5) , Mem( 256 Mi) , Disk
- 1 count of cpu meaning - 1 vCpu on aws , 1 GCP Core , 1 Azure Core , 1 hyperthread
- 100m  (0.1 CPU)
- default limit in kubernetes - 1vCPu and 512 Mi (memory)
- Exceed - throttle cpu if it tries to beyond limit
- Exceed- memory is allowed , but it will terminate if it is done constantly
- OOMKilled - memory issue