## Node Affinity

- Node Selectors are great for basic pod placement based on node labels. But **Node Affinity** feature offers advanced capabilities to fine-tune pod scheduling in your Kubernetes cluster.

- **Node Affinity** defines rules for Pods that can be scheduled based on node labels.

### Key Features:
- **Flexibility**: Define precise conditions for pod placement.
- **Control**: Decide where your pods can and cannot go with greater granularity.
- **Adaptability**: Allow pods to stay on their nodes even if the labels change after scheduling.

### Properties in Node Affinity
- ```requiredDuringSchedulingIgnoredDuringExecution```: The scheduler can't schedule the Pod unless the rule is met.
- ```preferredDuringSchedulingIgnoredDuringExecution```: If a matching node is not available, the scheduler still schedules the Pod.

### How it works:
- Define a Node label in your Pod 'spec'.
- Then Scheduler only places the Pod on nodes with matching labels.
- Once scheduled, the Pod remains on Node even if the label changes.

![image](https://github.com/Bhakti2304/CKA2024/assets/116799960/f646d9d2-89d3-499a-bcc7-a2a3eb8451b3)

Example YAML file:
```yaml
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: redis
  name: redis-new
spec:
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: disktype
            operator: In
            values:
            - ssd
      preferredDuringSchedulingIgnoredDuringExecution:
      - weight: 1
        preference:
          matchExpressions:
            - key: disktype
              operator: In
              values:
              - hdd  
  containers:
  - image: redis
    name: redis
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```
![image](https://github.com/Bhakti2304/CKA2024/assets/116799960/0ea7f6d5-2ffc-47d8-a242-ab609718ddf7)
