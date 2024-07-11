# Taints and Tolerations 

- A **Taint** marks a node with a specific characteristic, such as "gpu=true". By default, pods cannot be scheduled on tainted nodes unless they have a special permission called **Tolerations**. When a **toleration on a pod** matches with the **taint on the node** then only that *pod will be scheduled on that node*.

- **Taints** in Kubernetes allow users to specify rules for pod scheduling based on node attributes. **Tolerations** allow the scheduler to schedule pods with matching taints. **Taints** allow a node to repel a set of pods.

- **Taints** apply to Nodes and **Tolerations** apply to Pods.

- **Taints** and **Tolerations** work together to ensure that Pods are not scheduled onto inappropriate Nodes.

- **Taint** has key-value pair and effect. There are 3 types of Taint-effect available:
  1. NoSchedule: applied to newer pods
  2. PreferNoSchedule: No guarantee
  3. NoExecute: applied to all existing and newer pods

Syntax to add Taint to Node:

```bash
k taint node <node_name> <key>=<value>:<effect>
k taint node cka-cluster2-worker gpu=true:NoSchedule
```

- To remove the **Taint** :
```bash
k taint node cka-cluster2-worker gpu=true:NoSchedule-
```

- To add Toleration to Pod:
```yaml
spec:
  containers:
  - image: redis
    name: redis
  tolerations:
  - key: "gpu"
    operator: "Equal"
    value: "true"
    effect: "NoSchedule" 
```

## Taints vs Selectors

Taints work as restrictions applied on Nodes. Nodes make that decision on what type of Pods to accept.
In NodeSeletors, Pods take the decision on which Nodes it should go. We can not do expression and can not add more condiions.

