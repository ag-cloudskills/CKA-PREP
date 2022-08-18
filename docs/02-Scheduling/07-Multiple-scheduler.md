# scheduler

- custom scheduler can be created by creating the configuration 
- leader-elect property - it will help to select the master scheduler
- process to create a custom scheduler:
  - create a config map
  - create pod with custom scheduler definition 

- enable  schedulerName:  so that pod can use the custom scheduler


kubectl create -n kube-system configmap my-scheduler-config --from-file=/root/my-scheduler-config.yaml
