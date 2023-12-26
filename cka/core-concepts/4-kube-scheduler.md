# Kube Scheduler

Decides which pod goes on which node. It doesn't actually place the pod on the node.

Kube scheduler decides based on pod **resource requirements** and **taints/tolerations** and **nodeSelectors/affinity**.
+ Filters out the nodes that do not fit the pod requirement
+ Ranks nodes using priority function

To see options of Kube Controller Manager:
+ Hard way environment

 Kube scheduler at **/etc/systemd/system/kube-scheduler.service**
Provide a config file to the service 
```
--config=/etc/kubernetes/config/kube-scheduler.yaml
```
+ In a kubeadm
Deploys a pod of kube-scheduler in kube-system namespace on master node.  
cat kubernetes manifests folder **/etc/kubernetes/manifests/kube-scheduler.yaml**