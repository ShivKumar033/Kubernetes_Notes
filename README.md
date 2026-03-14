# Kubernetes Notes

This repository contains my learning notes for Kubernetes.

## Topics Covered
- Kubernetes Basics
- Kubernetes Architecture
- Cluster Setup (Minikube, Kind, Kubeadm)
- Kubernetes Objects
- Networking
- Storage
- Security
- Monitoring
- Real DevOps Projects

## Tools Covered
- kubectl
- Minikube
- Kind
- Kubeadm
- Helm


kubernetes-notes/
│
├── README.md
├── kubernetes-roadmap.md
│
├── 01-introduction
│   ├── what-is-kubernetes.md
│   ├── why-kubernetes.md
│   ├── monolithic-vs-microservices.md
│   └── kubernetes-history.md
│
├── 02-architecture
│   ├── kubernetes-architecture-overview.md
│   ├── control-plane.md
│   ├── worker-nodes.md
│   ├── api-server.md
│   ├── etcd.md
│   ├── scheduler.md
│   ├── controller-manager.md
│   └── kubelet-kubeproxy.md
│
├── 03-cluster-setup
│   ├── kind-cluster.md
│   ├── minikube-cluster.md
│   ├── kubeadm-setup.md
│   └── kubectl-basics.md
│
├── 04-kubernetes-objects
│   ├── pods.md
│   ├── replica-sets.md
│   ├── deployments.md
│   ├── daemonsets.md
│   ├── statefulsets.md
│   └── jobs-cronjobs.md
│
├── 05-networking
│   ├── services.md
│   ├── cluster-ip.md
│   ├── node-port.md
│   ├── load-balancer.md
│   ├── ingress.md
│   └── dns-in-kubernetes.md
│
├── 06-storage
│   ├── volumes.md
│   ├── persistent-volumes.md
│   ├── persistent-volume-claims.md
│   └── storage-classes.md
│
├── 07-configuration
│   ├── configmaps.md
│   ├── secrets.md
│   └── environment-variables.md
│
├── 08-security
│   ├── rbac.md
│   ├── service-accounts.md
│   ├── network-policies.md
│   └── security-best-practices.md
│
├── 09-monitoring-logging
│   ├── metrics-server.md
│   ├── prometheus.md
│   ├── grafana.md
│   └── logging.md
│
├── 10-troubleshooting
│   ├── common-errors.md
│   ├── kubectl-debug-commands.md
│   └── pod-debugging.md
│
├── 11-projects
│   ├── project-1-k8s-deployment.md
│   ├── project-2-microservice-app.md
│   └── project-3-ci-cd-kubernetes.md
│
└── assets
    ├── architecture-diagrams
    ├── images
    └── yaml-examples
