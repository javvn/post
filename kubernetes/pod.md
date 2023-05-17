# Keywords

- Represents a set of running containers in a cluster
- The smallest deployable unit ( single instance of a running process )
- Grouping one or more containers
- Two kinds of shared resources for their constituent containers: **network** and **storage**
- Ephemeral and Disposable

# Content

In Kubernetes, a pod is **the smallest deployable unit** that represents a single instance of a running process in a cluster. A pod can contain **one or more containers** that share the same **network** namespace and con access the same **storage volumes**. They are **scheduled to run on one of the nodes** in the cluster. Also facilitate the communication and data exchange between containers running in the same pod.

As well as application containers, a Pod con contain [init containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) that run during Pod startup. Also you can inject [ephemeral containers](https://kubernetes.io/docs/concepts/workloads/pods/ephemeral-containers/) for debugging if your cluster offers this.

Usually you are create pods using workload resources such as `Deployment` or `Job`. If your Pods need to track state, consider the `StatefulSet` resource.

Pods in Kubernetes cluster are used in **two main ways**:

- **Pods that run a single container.** The “one-container-per-Pod” model is the most common Kubernetes usecase.
- **Pods that run multiple containers that need to work together.** A Pod can encapsulate an application composed of multiple co-located containers that are tightly coupled and need to share resources. Grouping multiple co-located and co-managed containers in a single Pod is a relatively advanced usecase. You should use this pattern only in specific instances in which your containers are tightly coupled.

Each Pod is meant to run a single instance of a given application. If you want to scale your application horizontally ( to provide more overall resources by running more instances), you should use muliple Pods, one for each instance. In Kubernetes, this is typically referred to as `*replication*`.

Replicated Pods are usually created and managed as a group by a workload resource and its controller.

## Working with Pods

You’ll rarely create individual Pods directly in Kubernetes, even singleton Pods. This is because Pods are designed as relatively ephemeral, disposable entities.

`A Pod is not a process, but an environment for running container. A Pod persists until it is deleted.`

## Pods and controllers

A controller for the resource handles replication and rollout and automatic healing in case of Pod failure. If a Node fails, a controller notices that Pods on that Node have stopped working and creates a replacement Pod.

Workload resources that manage one or more Pods :

- **Deployment** : manages a replicated application on cluster.
- **StatefulSet** : manages deployment and scaling of a set of Pods, with durable storage and persistent identifiers for eash Pod
- **DaemonSet** : ensures a copy of a Pod is running across a set of nodes in cluster.

## Pod templates

Controllers for workload resources create Pods from a *pod template* and manage those Pods on your behalf.

`PodTemplates` are specifications for creating Pods, and are included in workload resources such as `Deployments`, `Jobs`, and `DaemonSets`.

The PodTemplate is part of the desired state of whatever workload resource you used to run your app.

## Pod update and replacement

When the Pod template for a workload resource is changed, the controller creates new Pods based on the updated template instead of updating or patching the existing Pods.

## Resource sharing and communication

Pods enable data sharing and communication among their constituent containers.

### [Storage](https://kubernetes.io/docs/concepts/storage/) in Pods

A Pod can specify a set of shared storage volumes. All containers in the Pod can access the shared volumes, allowing those containers to share data. Volumes also allow persistent data in a Pod to survive in case one of the containers within needs to be restarted.

### Pod [networking](https://kubernetes.io/docs/concepts/cluster-administration/networking/)

Each Pod is assigned a unique IP address for each address family. Every container in a Pod shares the network namespace, including the IP address and network ports. When containers in a Pod communicate with entities *outside the Pod*, then must coordinate how they use the shared network resources.

Within a Pod, containers share an IP address and port space, and can find each other via `localhost`. Containers in different Pods have district IP addresses and can not communicate by OS-level IPC without **special configuration**.

Containers within the Pod see the system hostname as being the same as the configured name for the Pod.

## Container [probes](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-probes)

A probe is a diagnostic performed periodically by the kubelet on a container. To perform a diagnostic, the kubelet can invoke different actions :

- `ExecAction` : performed with the help of the container runtime )
- `TCPSocketAction` : checked directly by the kubelet
- `HTTPGetAction` : checked directly by the kubelet

# References

[Pods](https://kubernetes.io/docs/concepts/workloads/pods/#pods-and-controllers)