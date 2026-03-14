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
```