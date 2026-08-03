# Kubernetes Microservice Demo

A production-style microservice deployment on Kubernetes. Demonstrates core workload primitives and cluster hygiene:

- **Deployments** with resource requests & limits (no noisy neighbors)
- **Services** (ClusterIP + LoadBalancer) for stable networking
- **Ingress** with path-based routing
- **ConfigMaps** for environment configuration
- **Secrets** for sensitive data

## Quick start

```bash
kubectl apply -f k8s/
kubectl get pods,svc,ingress
```

## Layout

- `k8s/deployment.yaml` - workload definition with liveness/readiness probes
- `k8s/service.yaml` - internal + external service exposure
- `k8s/ingress.yaml` - path-based routing rules
- `k8s/configmap.yaml` - non-sensitive configuration
- `k8s/secret.yaml` - sensitive configuration (example only)

## Why this matters

Resource limits prevent CPU/memory starvation; probes enable zero-downtime rollouts;
ConfigMaps/Secrets decouple config from images. These are the fundamentals of running
Kubernetes in production.
