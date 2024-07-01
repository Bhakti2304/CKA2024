# ClusterIP vs NodePort vs Loadbalancer vs External Names

1. NodePort: Through this service on which app will be exposes on particular Port.
The range for the NordPort from 30000 to 32767.
We have to specify Static port between this range, so application will be listening to this NodePort.
-Then Service will be expose internally within the cluster through Internal Service Port. All the sevices can access this Service through 80.
- We have another Port on which aplication will be listening, that is Target Port.

