# Kubernetes Deployment, Replication Controller and ReplicaSet

Each Pod has one container. We can create Pod in 2 methods:
    1. Imperative
    2. Declarative

    1. We can run simple commands. Instructing API server to do things with the help of kubectl command.

                 kubectl run nginx

    2. You create a configuration file, which could be JSON or YAML format. YAML highly use in Kubernetes.
    In that config. File you define desired status of object. 
    
   - Imperative use to troubleshoot or for local production.
   - Declarative use for Production deployment, creating CI/CD, also applicable for data option.
