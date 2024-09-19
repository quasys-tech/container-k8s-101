* service details, diagram.
* service types. nodeport, clusterip, loadbalancer.
* Pod - service networking.
* How Ingress work?
* Scheduling, labels and selectors.
* Taints and tolerations.
* Node Selector
* Resource reqiurements and limits.
* Secrets
* ETCD encrpytion
* liveness, readiness probes.
* Network Policy
* CNI - weave,calico,ovn-kubernetes
* DNS - Switching, routing.
* Authentication - kubeconfig.


Taint Node
------------

        kubectl taint node minikube dedicated=group1:NoSchedule
        kubectl create -f pod-nginx.yml
        kubectl get pods
        kubectl describe pods

Create Pod with Toleration
------------

        kubectl create -f pod-nginx-with-tolerations.yml
        kubectl get pods

Inspect Container Filesystem From K8s Host
------------

        crictl ps
        crictl inspect <Process-id> | grep -i pid
        cd /proc/<Process-id>
        cat /proc/<Process-id>/root/usr/share/nginx/html/index.html
        
