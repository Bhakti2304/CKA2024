# ClusterIP vs NodePort vs Loadbalancer vs External Names

1. NodePort: Through this service on which app will be exposed on particular Port.
The range for the NordPort is from 30000 to 32767.
We have to specify a Static port between this range,so the application will be listening to this NodePort.
- Then Service will be exposed internally within the cluster through Internal Service Port. All the services can access this Service through 80.
- We have another Port on which the application will be listening, that is Target Port.

 2. ClusterIp
 Let's we have multiple Pods running for Frontend and Backend. To communicate between frontend and backend Pods, they should have IP addresses of each other. There are internal IP addresses attached to the Pods, these are not Static IPs. Therefore when Pods restart, IP addresses will be changed.
