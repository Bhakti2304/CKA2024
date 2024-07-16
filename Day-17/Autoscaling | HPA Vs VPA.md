## Autoscaling | HPA Vs VPA

- **Scaling**: changes(increasing or decreasing) your server or workload to meet a demand
- Users accessing the application and load increases. App would fail, at sometime it will reach to the bottleneck, at sometime it will stop responding to the user or lot of latency responding to the request. In that case **horizontal pod autoscaling** uses.
- This autoscaling adds automatically identical pods in the deployment based on the  load on the server. This load can increase CPU or memory.
- It is also known as Scale out/in.
  

- For separate pod running, when app. faces some downtime uses  **vertical pod autoscaling** which resizes the pod in the deployment. 
- It is stateless in nature.
- It is also known as Scale up/down.

- **HPA** and **VPA** work based on metrics such as CPU, memory, disk, and so on.
- In some cases, we have to autoscale infrastructure or workload in the production system based on certain events such as getting lots of errors on one of the servers or lots of requests getting rejected on a particular node, then we should use 3rd party tools such as KEDA and Cron/Schedule based autoscaling.
  
  ![image](https://github.com/user-attachments/assets/3015e0c1-97de-4123-835d-b83c116f3411)

