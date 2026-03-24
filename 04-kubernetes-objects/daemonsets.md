A **DaemonSet** ensures that:
	 **One Pod runs on every node in the cluster**

### Key Points
- Automatically runs on new nodes
- Ideal for node-level services

## How DaemonSet Works

### Example Cluster:
- Node 1
- Node 2
- Node 3

 DaemonSet result:
- 3 Pods (1 per node)

If a new node is added:
- Node 4 → Pod automatically created 

**Example: DaemonSet YAML**
```php
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: fluentd-daemon
spec:
  selector:
    matchLabels:
      app: fluentd
  template:
    metadata:
      labels:
        app: fluentd
    spec:
      containers:
      - name: fluentd
        image: fluentd:latest
```

# Key Behavior

### 1. Auto-Scheduling per Node
- Kubernetes ensures each node runs one Pod
### 2. Auto Add / Remove

|Event|Action|
|---|---|
|New node added|Pod created|
|Node removed|Pod deleted|
### 3. Self-Healing
- If Pod crashes → recreated on same node
---
## Real-World Use Cases (VERY IMPORTANT)

### 1. Logging Agents
- Collect logs from each node

Examples:
- Fluentd
- Logstash
### 2. Monitoring Agents
- Collect metrics from nodes

Examples:
- Prometheus Node Exporter
### 3. Security Agents
- Antivirus / intrusion detection
### 4. Networking Components
- CNI plugins (like Calico)

