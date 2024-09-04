# container-k8s-101

Kubernetes

CRI: Container Runtime Interface (Container engines must support it for kubernetes.)

OCI (Open Container Initiative) has 2 domain imagespec, runtimespec.

Docker supported on kubernetes with dockershim until v1.24. After that version docker not supported as runtime. 
But images build with docker work, because docker support OCI imagespec. 

Openshift
  CRI-O as the container engine
  runC as the container runtime

OpenShift Container Platform uses a software-defined networking (SDN) approach to provide a unified cluster network that enables communication between pods across the OpenShift Container Platform cluster. This pod network is established and maintained by the OpenShift SDN, which configures an overlay network using Open vSwitch (OVS).
