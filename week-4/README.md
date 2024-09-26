Week 4
| K8s Component        | Documentation           |
| ------------- |:-------------:|
| Network Policies      | https://kubernetes.io/docs/concepts/services-networking/network-policies/ |
| Ingress      | https://kubernetes.io/docs/concepts/services-networking/ingress/      |
| ETCD | https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/      |

List API Resources from ETCDCTL
------------

      vagrant@container101-ubuntu:~$ kubectl get pods -n kube-system
      NAME                               READY   STATUS    RESTARTS        AGE
      coredns-6f6b679f8f-dd4n6           1/1     Running   3 (5d22h ago)   14d
      etcd-minikube                      1/1     Running   3 (5d22h ago)   14d
      kube-apiserver-minikube            1/1     Running   3 (5d22h ago)   14d
      kube-controller-manager-minikube   1/1     Running   3 (5d22h ago)   14d
      kube-proxy-vrsfh                   1/1     Running   3 (5d22h ago)   14d
      kube-scheduler-minikube            1/1     Running   3 (5d22h ago)   14d
      storage-provisioner                1/1     Running   7 (27m ago)     14d
      vagrant@container101-ubuntu:~$ kubectl exec -it etcd-minikube -n kube-system -- sh
      sh-5.2# export ETCDCTL_API=3
      sh-5.2# export ETCDCTL_ENDPOINTS="https://127.0.0.1:2379"
      sh-5.2# export ETCDCTL_CACERT="/var/lib/minikube/certs/etcd/ca.crt"
      sh-5.2# export ETCDCTL_CERT="/var/lib/minikube/certs/etcd/server.crt"
      sh-5.2# export ETCDCTL_KEY="/var/lib/minikube/certs/etcd/server.key"
      
      #Lists all resources in kubernetes.
      sh-5.2# etcdctl get / --prefix --keys-only
      
      sh-5.2# etcdctl get /registry/secrets/default/dotfile-secret
      /registry/secrets/default/dotfile-secret
      k8s
      
      
      v1Secret□
      □
      dotfile-secret␦default"*$a8f47255-e77e-4a71-ae96-62f5a1a8223f2□□Է□a
      kubectl-createUpdate␦v□□ԷFieldsV1:-
      +{"f:data":{".":{},"f:qwee":{}},"f:type":{}}B
      qwee
          value-2
      
      ␦Opaque␦"
