**Minikube** is a tool that runs a **single-node Kubernetes cluster locally**.

It is commonly used for:

- Learning Kubernetes
- Local development
- Testing Kubernetes applications

## Features

- Runs Kubernetes locally
- Supports addons (dashboard, ingress, metrics)
- Works with Docker, VirtualBox, or other drivers

## Installation

Install Minikube:
```php
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

Start cluster:
```php
minikube start

# start minikube cluster with extra node 
minikube start --nodes=3

# Allocate more CPU and RAM 
minikube start --cpus=4 --memory=8192
```

Check status:
```php
minikube status
```

Stop cluster:
```php
minikube stop
```

Delete cluster:
```php
minikube delete

# Delete the minikube node 
minikube node delete minikube-m02
```

## Visual representation
Single-node cluster:
```
+------------------------+
| Control Plane + Worker |
|      minikube          |
+------------------------+
```

Multi-node cluster:
```
        Kubernetes Cluster

        +-----------------------+
        |   Control Plane       |
        |      minikube         |
        +----------+------------+
                   |
        -------------------------
        |                       |
+---------------+      +---------------+
| minikube-m02  |      | minikube-m03  |
| Worker Node   |      | Worker Node   |
+---------------+      +---------------+
```