The **Control Plane** is responsible for **managing the Kubernetes cluster**.

It makes decisions such as:

- Scheduling pods
- Monitoring cluster state
- Handling API requests
- Maintaining desired state

## Components of Control Plane

```php
Worker Node
 ├── kubelet
 ├── kube-proxy
 ├── Container Runtime
 └── Pods
```

## Responsibilities

- Cluster management
- Resource scheduling
- State management
- Communication with worker nodes

Without the control plane, the cluster **cannot operate**.

---

# API Server

The **API Server** is the **front-end of the Kubernetes Control Plane**.

It acts as the **gateway to the Kubernetes cluster**.

All communication in Kubernetes goes through the API server.

## Responsibilities

- Handles REST API requests
- Validates requests
- Updates cluster state
- Communicates with etcd

Example Flow:
```php
kubectl apply -f deployment.yaml
        │
        ▼
   API Server
        │
        ▼
       etcd
```

The API server ensures that **all cluster operations follow Kubernetes rules**.

---

# etcd

**etcd** is a **distributed key-value store** used to store all cluster data.

It acts as the **database of Kubernetes**.

## What etcd Stores

- Cluster configuration
- Pod information
- Node details
- Secrets and configs

Example stored data:
```php
Cluster State
 ├── Pods
 ├── Nodes
 ├── Services
 └── Configurations
```

## Key Features

- Highly available
- Distributed
- Consistent
- Reliable

If **etcd data is lost**, the entire cluster state is lost

---

# Scheduler

The **Kubernetes Scheduler** decides **where to run pods**.

When a new pod is created, the scheduler selects the **best node** to run it.

## Scheduling Factors

The scheduler checks:
- CPU availability
- Memory availability
- Node health
- Resource requirements
- Node labels
- Taints and tolerations

Scheduler Flow:
```php
New Pod Created
      │
      ▼
Scheduler selects best node
      │
      ▼
Pod assigned to node
```

The scheduler ensures **efficient resource usage**. 

---

# Controller Manager

The **Controller Manager** ensures that the **cluster matches the desired state**.

Example:

If a pod crashes, the controller manager creates a **new pod automatically**.

## Controllers Included

- Node Controller
- Replication Controller
- Deployment Controller
- Endpoint Controller
- Namespace Controller

Example:
```php
Desired state:
	3 Pods Running

Actual state:
	2 Pods Running

Controller Manager action:
	Creates 1 new pod
```
This is called **reconciliation**.