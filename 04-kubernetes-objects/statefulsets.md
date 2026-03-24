A **StatefulSet** is used to manage **stateful applications** where each Pod needs:

- Stable identity
- Persistent storage
- Ordered deployment

	Unlike Deployments, Pods are **not identical or interchangeable**

## Core Idea (Very Important)

StatefulSet provides **3 guarantees**:

## #1.Stable Pod Identity

Pods have fixed names:
```php
mysql-0
mysql-1
mysql-2
```
Even after restart, names remain same

### 2. Persistent Storage

Each Pod gets its **own volume**:
- mysql-0 → volume-0
- mysql-1 → volume-1

Data is NOT lost if pod restarts

### 3. Ordered Deployment & Scaling

Pods are created **in sequence**:
```php
mysql-0 → mysql-1 → mysql-2
```

Deletion is reverse:
```php
mysql-2 → mysql-1 → mysql-0
```

 **Example: StatefulSet YAML**
 ```php
 apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: "mysql-service"
  replicas: 2
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
      - name: mysql
        image: mysql:5.7
        ports:
        - containerPort: 3306
  volumeClaimTemplates:
  - metadata:
      name: mysql-storage
    spec:
      accessModes: ["ReadWriteOnce"]
      resources:
        requests:
          storage: 1Gi
 ```

## Stable Network Identity (Very Important)

Each Pod gets a **DNS name**:
```php
mysql-0.mysql-service
mysql-1.mysql-service
```
 Used for:
- Database clusters
- Leader election
- Replication

# What Happens During Restart?

- Pod dies → recreated with same name
- Same volume reattached
- Data persists 