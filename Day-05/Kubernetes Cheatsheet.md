## kubectl Configurations

```
kubectl config current-context  
```
**View current context**
kubectl config use-context <context_name>

**Switch context**
kubectl config get-contexts
**View all contexts**

## Pods

kubectl get pods
**List all pods**

kubectl describe pods <pod_name>
**Get pod details**

kubectl create pod <pod_name>
**Create a pod**

kubectl delete pod <pod_name>
**Delete a pod**

kubectl run<pod_name> —-image=<image_name>
**launch a pod with a name and an image**

kubectl port-forward <pod name> <port_number_to_listen_on>:<port_number_to_forward_to>
**Listen on a port on the local machine and forward to a port on a specified pod**

## Deployments

kubectl get deployments
**List all deployments**

kubectl describe deployment <deployment_name>
**Get deployment details**

kubectl create deployment <deployment_name> --image=<image_name>
**Create a deployment**

kubectl edit deployment <deployment_name>
**Edit and update the definition of one or more deployments on the server**

kubectl delete deployment <deployment_name>
**Delete deployments**

kubectl scale deployment <deployment_name> --replicas=<number_of_replicas>
**Scale a deployment**

kubectl rollout status deployment <deployment_name> 
**See the rollout status of a deployment**

kubectl set image deployment/<deployment_name> <container_name>=<new_image>
**Update a deployment**

kubectl set image deployment/<deployment_name> <container_name>=image:<new_image_version>
**Perform a rolling update (K8S default), set the image of the container to a new version for a particular deployment**

kubectl rollout undo deployment/<deployment_name>
**Rollback a previous deployment**

## Services

kubectl get services/svc
**List all services**

kubectl describe service/svc <service_name>
**Get service details**

kubectl expose deployment <deployment_name> --type=<service_type> --port=<port> --target-port=<target_port>
**Expose a deployment as a service**

## ConfigMaps and Secrets

kubectl get configmaps
**List all configmaps**

kubectl create configmap <configmap_name> --from-literal=<key>=<value>
**Create a configmap**

kubectl get secrets
**List all secrets**

kubectl create secret generic <secret_name> --from-literal=<key>=<value>
**Create a secret**

## Namespaces

kubectl get namespaces
**List all namespaces**

kubectl create namespace <namespace_name>
**Create a namespace**

kubectl delete namespace <namespace_name>
**Delete a namespace**

## Logs

kubectl logs <pod_name>
**View logs of a pod**

kubectl logs <pod_name> -c <container_name>
**View logs of a specific container in a pod**

kubectl logs -f <service_name> [-c <$container>] 
**Get logs from a service and optionally select which container**

kubectl logs <pod_name> pod.log 
**Output the logs for a pod into a file named ‘pod.log’**

## Port Forwarding

kubectl port-forward pod/<pod_name> <local_port>:<pod_port>
**Forward a local port to a port on a pod**

## Executing Commands in Pods

kubectl exec -it <pod_name> -- <command>
**Execute a command in a pod**

## Configuration Files (Also referred to as Manifest or YAML Files)

kubectl create -f <configuration_file>  
**Create objects**

kubectl create -f <configuration_file_directory> 
**Create objects in all manifest files in a directory**

kubectl create -f <‘url’> 
**Create objects from a URL**

kubectl delete -f <configuration_file> 
**Delete an object**

## Replication Controllers

kubectl get rc
**List the replication controllers**

kubectl get rc --namespace=”<namespace_name>” 
**List the replication controllers by namespace**

## Replica Sets

kubectl get replicasets/rs
**List ReplicaSets**

kubectl describe replicasets/rs <replicaset_name>
**Display the detailed state of one or more ReplicaSets**

kubectl scale --replicas=[x] 
**Scale a ReplicaSet**

kubectl create -f <rs.yaml>
**Create a new ReplicaSet using a YAML file**

## Persistent Volumes and Persistent Volume Claims

kubectl get pv
**List all persistent volumes**

kubectl get PVC
**List all persistent volume claims**

## Miscellaneous

kubectl cluster-info
**Get cluster information**

kubectl api-resources
**View the API resources**

## Tips

kubectl get pods -o yaml
**Use -o yaml or -o json to output resources in YAML or JSON format**

kubectl apply -f <file>.yaml
**Use kubectl apply -f <file> to create/update resources defined in a YAML/JSON file**

kubectl delete -f <file>.yaml
**Use kubectl delete -f <file> to delete resources defined in a YAML/JSON file**

