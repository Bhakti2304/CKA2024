## Daemonsets, Job and Cronjob in Kubernetes

### Cronjob

-  Cronjob is basically a type of job, that we execute at a certain time on a certain day or after an interval, we specify that schedule with the help of ``` schedule: "* * * * *" ``` format. It is mostly based on a Linux-based system. It will make sure that script or build is triggered at that particular schedule that we have specified.

- To automate time-based job execution
``` * * * * * ```
- 1st * shows Minute, allowed value 0-59
- 2nd * shows Hour, allowed value 0-23
- 3rd * shows Day of Month, allowed value 1-31
- 4th * shows Month, allowed value 1-12
- 5th * shows Day of Week, allowed value 0-6 (Sunday to Saturday)

Example: 
- For every Saturday
``` * * * * 6```
- For every Saturday at 11 pm
```* 23 * * 6```
- For every Saturday at 11:45 Pm
```45 23 * * 6```
- For every 5 minutes */n to every nth interval of time
- ```*/5 * * * *```
