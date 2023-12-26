# ETCD
Two API versions of etcd, 2 and 3

To set version of etcd api
```
export ETCDCTL_API=3
```
Set certs to authenticate etcdctl with etcd API server.
Certs are available at the following path in etcd-master.
```
--cacert /etc/kubernetes/pki/etcd/ca.crt
--cert /etc/kubernetes/pki/etcd/server.crt
--key /etc/kubernetes/pki/etcd/server.key
```
Commands in version 3
```
etcdctl snapshot save
etcdctl endpoint health
etcdctl get
etcdctl put
```

