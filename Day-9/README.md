# ClusterIP vs NodePort vs Loadbalancer vs External Names

1. NodePort: Through this service on which app will be exposed on particular Port.
The range for the NordPort is from 30000 to 32767.
We have to specify a Static port between this range, so the application will be listening to this NodePort.
-Then Service will be exposed internally within the cluster through Internal Service Port. All the services can access this Service through 80.
- We have another Port on which application will be listening, that is Target Port.

