## Static pods, Manual scheduling, Labels, and Selectors in Kubernetes

### Static pods

Static Pods are managed directly by the kubelet on a specific node rather than being managed by the Kubernetes API server.

**Key Characteristics of Static Pods:**
- **Not Managed by the Scheduler**: Unlike deployments or replicasets, the Kubernetes scheduler does not manage static pods.
- **Defined on the Node**: Configuration files for static pods are placed directly on the node's file system, and the `kubelet` watches these files.
- **Some examples of static pods are:** ApiServer, Kube-scheduler, controller-manager, ETCD etc
  
**Managing Static Pods:**
1. **SSH into the Node**: You will gain access to the node where the static pod is defined.(Mostly the control plane node)
2. **Modify the YAML File**: Edit or create the YAML configuration file for the static pod.
3. **Remove the Scheduler YAML**: To stop the pod, you must remove or modify the corresponding file directly on the node.
4. **Default location**": is usually `/etc/kubernetes/manifests/`; you can place the pod YAML in the directory, and Kubelet will pick it for scheduling.

### Manual Pod Scheduling

Manual Pod Scheduling in Kubernetes refers to the process of assigning pods to specific nodes without relying on the Kubernetes scheduler.

**Key Points:**
- **`nodeName` Field**: Use this field in the pod specification to specify the node where the pod should run.
- **No Scheduler Involvement**: When `nodeName` is specified, the scheduler bypasses the pod, and it’s directly assigned to the given node.

**Example Configuration:**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  nodeName: cka-cluster2-worker
  containers:
  - name: nginx
    image: nginx
```

>Note: Kubernetes will place the pod on cka-cluster2-worker with the above configuration.

### Labels

Labels are key-value pairs attached to Kubernetes objects like pods, services, and deployments. They help organize and group resources based on criteria that make sense to you.

### Selectors
Selectors filter Kubernetes objects based on their labels. This is incredibly useful for querying and managing a subset of objects that meet specific criteria.

**Common Usage:**
- **Pods**: `kubectl get pods --selector app=my-app`
- **Deployments**: Used to filter the pods managed by the deployment.
- **Services**: Filter the pods to which the service routes traffic.

### Labels vs. Namespaces
- **Labels**: Organize resources within the same or across namespaces.
- **Namespaces**: Provide a way to isolate resources from each other within a cluster.
