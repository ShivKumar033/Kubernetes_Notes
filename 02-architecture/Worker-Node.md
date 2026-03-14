Worker nodes are machines where **actual applications run**.

Each worker node contains:
```php
Worker Node
 ├── kubelet
 ├── kube-proxy
 ├── Container Runtime
 └── Pods
```

## Responsibilities

- Running application containers
- Communicating with the control plane
- Maintaining pod health
- Handling networking

Worker nodes can be:

- Physical machines
- Virtual machines
- Cloud instances

---

## kubelet

The **kubelet** is an agent running on every worker node.

It communicates with the **API Server**.

Responsibilities:

- Ensures containers are running
- Monitors pod health
- Executes pod instructions

Example flow:
```php
API Server → kubelet → Container Runtime → Run Pod
```

---

## kube-proxy

The **kube-proxy** manages **network communication between pods**.

It handles:

- Service networking
- Load balancing
- Network rules

Example:
```php
User Request
     │
     ▼
Service
     │
     ▼
kube-proxy routes traffic
     │
     ▼
Pod
```

---

### Simple Kubernetes Architecture Flow

```php
Developer
   │
   ▼
kubectl
   │
   ▼
API Server
   │
   ▼
etcd (stores state)
   │
   ▼
Scheduler assigns pod
   │
   ▼
Worker Node
   │
   ├── kubelet runs container
   └── kube-proxy manages networking
```