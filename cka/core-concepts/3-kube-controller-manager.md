# Kube Controller Manager
All controllers are packaged in the kubernetes-controller-manager.

Manages various controllers for different k8s objects. These are process that continously watch the state and brings state to desired state.
+ Continously watch status
+ Remediate situation

## Node controller 
Watches the status of the nodes every 5s. If node-controller do not gets heartbeat from the node it marks it as `unreachable`.

Gets heartbeat every 5s, waits 40s before marking unreachable and evicts pods after 5mins.
```
Node monitor period = 5s 
Node monitor grace period = 40s
POD Eviction timeout = 5m //time given to node to come back up
```
## Replication controller
Watches for the desired number of pods

All the k8s components have controllers. 
+ PV Binder controller
+ Endpoint controller
+ Namespace controller
+ Service Account controller

## Install Kube Controller manager
Run kube-controller-manager.service
In this service additional options are provided.
`e.g` controllers option to specify which controllers to enable
```
--node-monitor-period=5s
--node-monitor-grace-period=40s
--pod-eviction-timeout=5m0s
--controllers stringSlice
```

To see options of Kube Controller Manager:
+ Hard way environment

 Kube contoller manager at **/etc/systemd/system/kube-controller-manager.service**

+ In a kubeadm

cat kubernetes manifests folder **/etc/kubernetes/manifests/kube-controller-manager-master.yaml**
