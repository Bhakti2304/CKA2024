## Health Probes

- Probe is monitoring your system and taking necessary actions to either recover the health or make sure everything is working fine. 

- Health probes are used to determine the health and readiness of a pod. These probes help Kubernetes manage the lifecycle of pods by restarting them when they are unhealthy or delaying their traffic until they are ready. 

- There are 3 types of Health Probes:

1. Startup - Used to check if the application within the pod has started. It is mostly used for slow/legacy applications that take the most time to startup.
2. readiness - Determines if a pod is ready to handle traffic. It ensures your application is ready before it starts serving the traffic to the user.
3. liveness - Checks if the application inside a pod is running. It monitors the apps after a certain period of time and when the application fails or crashes, it restarts the application. 
