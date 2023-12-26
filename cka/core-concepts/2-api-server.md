# API Server
Kube API server authenticates and validates `kubectl` commands
+ authenticated
+ validated
+ retreive and update data in etcd


Scheduler continously monitors api server and watches for new pods created.

Once `scheduler identifies` a node, this info is passed to `api server` which updates in `etcd` and also informs to `kubelet` on the right node. kubelet then instructs `container runtime` to deploy the image of application. Once done `kubelet` informs back to `api server`.

Kube API server is available as a binary on k8s release page. Download and configure it to run as a service on master node.

Location to specify etcd server to connect it with `api server`
```
--etcd-servers=https:127.0.0.1:2379 \\
```

To view kube API server options in a cluster. 

Kubeadm tool deploys a pod of kube api server in `kube system` namespace. Name of pod is `kube-apiserver-master`

To see options of Kube API server:
+ Hard way environment

 Api server at **/etc/systemd/system/kube-apiserver.service**

+ In a kubeadm

cat kubernetes manifests folder **/etc/kubernetes/manifests/kube-apiserver.yaml**

