![[kubernetes-cluster-architecture.svg]]
Kubernetes follows a **master–worker architecture** (now commonly called **Control Plane and Worker Nodes**).

A Kubernetes cluster contains:
```php
Kubernetes Cluster
 ├── Control Plane
 └── Worker Nodes
```

The **Control Plane** manages the cluster, while **Worker Nodes run the applications**.

## Main Components

### Control Plane Components

- API Server
- Scheduler
- Controller Manager
- etcd

### Worker Node Components

- kubelet
- kube-proxy
- Container Runtime
- Pods

## How It Works (High Level)

1. Developer sends request using `kubectl`
2. Request goes to **API Server**
3. Data is stored in **etcd**
4. **Scheduler** decides where to run the pod
5. **Controller Manager** ensures desired state
6. **Worker Node** runs the container