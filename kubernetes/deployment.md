# Keywords

- Manage a replicated application on cluster.

# Content

---

A *Deployment* provides declarative updates for `Pods` and `ReplicaSets`.

Describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.

# Writing a Deployment Spec

When the control plane creates new Pods for a Deployment, the `.metadata.name` of the Deployment is part of the basis for naming those Pods.

## Pod Template

The `.spec.template` is a Pod template. It has exactly the sma schema as a Pod, except it is nested and does not have an `apiVersion` or `kind`.

## Replicas

`.spec.replicas` is an optional field that specifies the number of desired Pods. It defaults to 1.

## Selector

`.spec.selector` is a required field that specifies a label selector for the Pods targeted by this Deployment. `.spec.selector` must match `.spec.template.metadata.labels`, or it will be rejected by the API.

`.spec.selector` is immutable after creation of the Deployment in `apps/v1`.

## Strategy

`.spec.strategy` specifies the strategy used to replace old Pods by new ones. `.spec.strategy.type` can be “`Recreate`” of “`RollingUpdate`”. The default value is “RollingUpdate”.

### Recreate Deployment

All existing Pods are killed before new ones are created when `.spec.strategy.type==Recreate`.

### Rolling Update Deployment

The Deployment updates Pods in a rolling update fashion when `**.spec.strategy.type==RollingUpdate`.** You can specify `maxUnavailable` and `maxSurge` to control the rolling update process.

**Max Unavailable**

`.spec.strategy.rollingUpdate.maxUnavailable` is an optional field that specifies the maximum number of Pods that **can be unavailable during the update process**. The value can be an absolute number or a percentage of desired Pods. The value cannot be 0 if `.spec.strategy.rollingUpdate.maxSurge` is 0. The default value is 25%.

**Max Surge**

`.spec.strategy.rollingUpdate.maxSurge` is an optional field that specifies the maximum number of Pods that **can be created over the desired number of Pods**. The value cannot be 0 if `MaxUnavailable` is 0.

# References

[Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)