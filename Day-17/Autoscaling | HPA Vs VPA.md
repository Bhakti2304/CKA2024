## Autoscaling | HPA Vs VPA

- Scaling: changes(increasing or decreasing) your server or workload to meet a demand
- Users accessing the application and load increases. App would fail, at sometime it will reach to the bottleneck, at sometime it will stop responding to the user or lot of latency responding to the request. In that case **horizontal pod autoscaling** uses.
- This autoscaling adds identical pods in the deployment automatically based on the  load on the server. This load can be increase CPU or memory.
- 
