# Content

Each object has a *Name* that is **unique** for that **type of resource**. Every Kubernetes object also has a ***UID*** that is **unique across your whole cluster.**

For non-unique user-provided attributes, Kubernetes provides `labels` and `annotations`.

## Names

A Client-provided string that refers to an object in a resource URL, such as `/api/v1/pods/some-name`.

Only one object of a given kind can have a given name at a time. However, if you delete the object, you can make a new object with the same name.

**Names must be unique acroos all API versions of the same resource.**

Four types of commonly used name constraints for resources.

## DNS Subdomain Names

- Contain no more than 253 characters.
- Contain only lowercase alphanumeric characters, ‘-’ or ‘.’
- Start with an alphanumeric character.
- End with an alphanumeric character.

## RFC 1123 Label Names

- Contain at most 63 characters.
- Contain only lowercase alphanumeric characters of ‘-’
- Start with an alphanumeric character.
- End with an alphanumeric character.

## Path Segment Names

Some resource types require their names to be able to be safely encoded as a path segment. In other words, the name may not be “.” or “..” and the name may not contain “/” or “%”.

## UIDs

A Kubernetes systems-generated string to uniquely identify objects.

Every object created over the whole lifetime of a Kubernetes cluster has a distinct UID. it is intended to distinguish between historical occurrences of similar entities.

# References

[Object Names and IDs](https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#dns-subdomain-names)