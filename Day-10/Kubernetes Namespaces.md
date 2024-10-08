# Kubernetes Namespaces

- In Kubernetes, a namespace is a way to divide cluster resources between multiple users.  They provide a mechanism for isolating resources such as services, pods, and deployments within the same cluster.
- Resources resides within namespaces interact with each other through their Hostnames.
- Resources resides in different namespaces interact with eachother through fully qualified domain name.


## Common Use Cases for Namespaces
- **Separation of environments**: Separate namespaces for development, testing, and production.
- **Multi-tenancy**: Different teams or projects can have their own namespaces to ensure isolation.


![alt text](namespace.png)

