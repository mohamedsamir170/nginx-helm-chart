# nginx Helm Chart

A simple Helm chart for deploying nginx.

## Installation

```bash
helm install my-nginx .
```

## Configuration

The following table lists the configurable parameters and their default values:

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of nginx replicas | `1` |
| `image.repository` | nginx image repository | `nginx` |
| `image.tag` | nginx image tag | `1.25` |
| `image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `service.type` | Kubernetes service type | `ClusterIP` |
| `service.port` | Service port | `80` |
| `service.targetPort` | Container port | `80` |
| `resources.limits.cpu` | CPU limit | `500m` |
| `resources.limits.memory` | Memory limit | `512Mi` |
| `resources.requests.cpu` | CPU request | `250m` |
| `resources.requests.memory` | Memory request | `256Mi` |

## Examples

### Install with custom replica count

```bash
helm install my-nginx . --set replicaCount=3
```

### Install with custom service type

```bash
helm install my-nginx . --set service.type=LoadBalancer
```

### Install with custom values file

```bash
helm install my-nginx . -f my-values.yaml
```
