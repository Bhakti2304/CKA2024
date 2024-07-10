# Kubernetes Deployment, Replication Controller and ReplicaSet

Each Pod has one container. We can create Pod in 2 methods:
    1. Imperative
    2. Declarative

    1. We can run simple commands. Instructing API server to do things with the help of kubectl command.

                 kubectl run nginx

    2. You create a configuration file, which could be JSON or YAML format. YAML highly use in Kubernetes.
    In that config. File you define the desired status of object. 
    
   - Imperative use to troubleshoot or for local production.
   - Declarative use for Production deployment, creating CI/CD, also applicable for data option.

## Cheatsheet for Kubernetes commands:

https://kubernetes.io/docs/reference/kubectl/quick-reference/

## ReplicaSet

A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical Pods.
https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/

## Deployments

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.

https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

## ReplicationController

A ReplicationController ensures that a specified number of pod replicas are running at any one time. In other words, a ReplicationController makes sure that a pod or a homogeneous set of pods is always up and available.

https://kubernetes.io/docs/concepts/workloads/controllers/replicationcontroller/
