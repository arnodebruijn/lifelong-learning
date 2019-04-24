Kubernetes
==========
Kubernetes is an open source orchestration system for managing containerized applications across multiple hosts; providing basic mechanisms for deployment, maintenance, and scaling of applications.


Features
--------
- self-healing
- auto-placement
- auto-restart
- auto-replication
- auto-scaling
- rolling updates/rollbacks

Kubernetes Objects
------------------

### Pods
One or more containers that are guaranteed to be co-located on the host
machine and can share resources. Tied together for the purpose of
administration and networking. Containers should only be scheduled
together in a single pod if they are tightly coupled and need to share
resources such as disk.
(a group of whales is called a pod, just like a group of containers can run on a pod)

### Services
A set of pods that work together, such as one tier of a multi-tier
application.

### Volumes
Persistent storage that exists for the lifetime of the pod itself.

### Namespaces
Partitioning of the resources Kubernetes manages into non-overlapping sets.



Architecture
------------
A Kubernetes cluster consists of two types of resources:

### Kubernetes Master
The master coordinates all activities in your cluster, such as scheduling
applications, maintaining applications desired state, scaling applications
and rolling out new updates.

### Kubernetes Node
Also known as a worker or minion, is a VM or machine where containers are
deployed.



Nomenclature
------------

Kubelet     an agent for managing the node and communicating with the
            Kubernetes master.

Kubectl     command line tool to deploy and manage applications on K8.


Minikube    a local k8 cluster for development and testing.


Ingress     an object that allows access to your Kubernetes services
            from outside the cluster

Deployment  manage the creation and scaling of pods, checks on the health
            of your pod and restart the pod's container if it terminates.

Helm        manages Kubernetes charts (packages of pre-configured
            Kubernetes resources)

etcd        a distributed key value store that provides a reliable way to
            store data accross multiple machines

replicaset  

Setup
=====

Hosted
------
AWS EKS       Elastic container service for Kubernetes
Openshift     Hybrid cloud Kubernetes platform


On-premise turn key
-------------------
Docker Enterprise
Kublr
Openshift Container Platform
Rancher



Things to consider
------------------
Vendor lock-in
Possibility to migrate from west to cloud and vice versa


