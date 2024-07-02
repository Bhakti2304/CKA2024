## kubectl Configurations

kubectl config current-context
**View current context**

kubectl config use-context <context-name>
**Switch context**

kubectl config get-contexts
**View all contexts**

## Pods

kubectl get pods
**List all pods**

kubectl describe pod <pod-name>
**Get pod details**

kubectl delete pod <pod-name>
**Delete a pod**

## Deployments

kubectl get deployments
**List all deployments**

kubectl describe deployment <deployment-name>
**Get deployment details**

kubectl create deployment <deployment-name> --image=<image-name>
**Create a deployment**

kubectl edit deployment <deployment_name>
**Edit and update the definition of one or more deployments on the server**

kubectl delete deployment <deployment_name>
**Delete deployments**

kubectl scale deployment <deployment-name> --replicas=<number-of-replicas>
**Scale a deployment**

kubectl rollout status deployment <deployment_name> 
**See the rollout status of a deployment**

kubectl set image deployment/<deployment-name> <container-name>=<new-image>
**Update a deployment**

kubectl set image deployment/<deployment_name> <container_name>=image:<new_image_version>
**Perform a rolling update (K8S default), set the image of the container to a new version for a particular deployment**

kubectl rollout undo deployment/<deployment_name>
**Rollback a previous deployment**

## Services

kubectl get services
**List all services:**

kubectl describe service <service-name>
**Get service details**

kubectl expose deployment <deployment-name> --type=<service-type> --port=<port> --target-port=<target-port>
**Expose a deployment as a service**

## ConfigMaps and Secrets

kubectl get configmaps
**List all configmaps**

kubectl create configmap <configmap-name> --from-literal=<key>=<value>
**Create a configmap**

kubectl get secrets
**List all secrets**

kubectl create secret generic <secret-name> --from-literal=<key>=<value>
**Create a secret**

## Namespaces

kubectl get namespaces
**List all namespaces**

kubectl create namespace <namespace-name>
**Create a namespace**

kubectl delete namespace <namespace-name>
**Delete a namespace**

## Logs

kubectl logs <pod-name>
**View logs of a pod**

kubectl logs <pod-name> -c <container-name>
**View logs of a specific container in a pod**

kubectl logs -f <service_name> [-c <$container>] 
**Get logs from a service and optionally select which container**

kubectl logs <pod_name> pod.log 
**Output the logs for a pod into a file named ‘pod.log’**

## Port Forwarding

kubectl port-forward pod/<pod-name> <local-port>:<pod-port>
**Forward a local port to a port on a pod**

## Executing Commands in Pods

kubectl exec -it <pod-name> -- <command>
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

