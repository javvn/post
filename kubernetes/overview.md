# Overview

- Management containerized workloads and services
- Facilitates both declarative configuration and automation
- Portable, Extensible, open source platform

# Background

## Traditional deployment era

- Organizations ran application on physical servers
- No way to define resource boundaries for applications in physical server
- This caused resource allocation issues.
- A solution for this would be to run each application on a diffrenent physical server.
- But this did not scale as resources were underutilized, and it was expensive for organizations to maintain many physical servers.

## Virtualized deployment era

- As a solution, virtualization was introduced.
- It allows you to run multiple Virtual Machines on a single physical server’s CPU.
- Virtualization allows applications to be isolated between VMs and provides a level of security as the information of one application cannot be freely accessed by another application

## Container deployment era

- Similar to VMs.
- But containers have relaxed isolation to share OS among the applications.
- So containers are considered lightweight.
- A container has its own filesystem, share of CPU, memory, processes space and more
- Benefits of using container :
    - Agile application creation and deployment
    - Continuous deployment, integretion
        - reliable and frequent container image build and deployment with quick and efficient rollbacks ( due to image immutability )
    - Observability
    - Environmental consistency
    - Distribution portability
    - Loosely coupled, distributed, elasic, liberated micro-services
    - Resource isolation
        - predictable application performance
    - Resource utilization

# Why need Kubernetes ?

Containers are a good way to bundle and run applications. In a production, need to manage the containers that run applications and ensure that there is no downtime. If a container goes down, another container needs to start. How do you solve it ? That’s how Kubernetes comes to the rescue !

Kubernetes provides :

### Service discovery and load balancing

- Expose a container using DNS name of using their own ip address
- If traffic to a container is high, able to load balance and distribute the network traffic.

### Storage orchestration

- Allows you to automatically mount a storage system
- Storage system such as … :
    - local
    - publuc cloud provider
    - more..

### Automated rollouts and rollbacks

- Can describe the desired state for your deployed containers
- Can change the actual state to desired state

### Automatic bin packing

- Tell kubernetes how much CPU and memory each container needs
- Can fit container onto your nodes to make the best use of your resources

### Self-healing

- Restart containers that fail, replace container, kill containers that don’t respond to your user-defined health check

### Secret and configuration management

- Let you store and manage sensitive information
- Can deploy and update secrets and application configuration without rebuilding your container images, and without exposing secrets in your stack configuration.

# What Kubernetes is not

Kubernetes is not a traditional, all-inclusive PaaS system. Operating at the container level rather than at the hardware level. It provides some generally applicable features common to PaaS offerings, such as deployment, scaling, load balancing, and lets users integrate their logging, monitoring, and alerting solutions.

# References

[Overview](https://kubernetes.io/docs/concepts/overview/)