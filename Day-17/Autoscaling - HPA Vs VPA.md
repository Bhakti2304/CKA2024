## Autoscaling | HPA Vs VPA

- **Scaling**: changes(increasing or decreasing) your server or workload to meet a demand


  ![image](https://github.com/user-attachments/assets/3015e0c1-97de-4123-835d-b83c116f3411)
  
- Users accessing the application and load increases. Application would fail, at some time it will reach to the bottleneck, at some time it will stop responding to the user or lot of latency responding to the request. In that case **Horizontal Pod Autoscaling** uses.
- **Horizontal Pod Autoscaling (HPA)** automatically adds identical pods in the deployment, or replica set based on the load on the server. This load can increase CPU or memory utilization.
- It is also known as 'Scale out/in'.

- For separate pod running, when the application faces some downtime, it uses  **Vertical Pod Autoscaling** which resizes the pod in the deployment.
- **Vertical Pod Autoscaling (VPA)** automatically adjusts the CPU and memory requests/limits of your pods to ensure they have the right amount of resources.
- It is stateless and also known as 'Scale up/down'.

- **HPA** and **VPA** work based on metrics such as CPU, memory, disk, and so on.
- In some cases, we have to autoscale infrastructure or workload in the production system based on certain events such as getting lots of errors on one of the servers or lots of requests getting rejected on a particular node, then we should use 3rd party tools such as KEDA and Cron/Schedule based autoscaling.
  

![HPA vs VPA](https://github.com/user-attachments/assets/681d3df7-3e19-4e9a-b470-c870f98af4c1)

