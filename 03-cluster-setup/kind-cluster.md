**KIND (Kubernetes IN Docker)** is a tool used to run **local Kubernetes clusters using Docker containers as nodes**.

It is mainly used for:

- Kubernetes testing
- Local development    
- CI/CD pipelines

## Why Use KIND?

- Lightweight
- Fast cluster creation
- Good for testing Kubernetes configurations
- Runs inside Docker containers

## Installation

Install Docker first.

Then install KIND:
```php
curl -Lo ./kind https://kind.sigs.k8s.io/dl/latest/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/
```

Create a Cluster:
```php
kind create cluster
```

Check cluster:
```php
kubectl cluster-info
```

Delete cluster:
```php
kind delete cluster
```