# Kubernetes

TrevVM-2 can be deployed using the repository's Kubernetes manifest:

```bash
kubectl apply -f https://raw.githubusercontent.com/dockur/windows/refs/heads/master/kubernetes.yml
```

Before applying, review the manifest and ensure that:

- Cluster nodes support KVM.
- `/dev/kvm` is accessible.
- Storage and resource limits meet your needs.
- Network ports are allowed by cluster security rules.
- Persistent storage is configured if required.

Consult the repository README for full deployment details.
