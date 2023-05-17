# Keywords

- Guarantee the availability of a specified number of identical Pods.

# Content

A ReplicaSet is a controller that ensures a specified number of replicas of a pod are running in a cluster at all times. The ReplicaSet’s purpose is to maintain a stable set of replica Pods running at any given time.

ReplicaSets help to ensure high availability and scalability by automatically scaling the number of Pod replicas up or down in response to changes in demand or hardware failures.

They are responsible for monitoring the status of Pods and creating or deleting replicas as necessary to meet the desired state.

# References

[ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)