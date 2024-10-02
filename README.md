# Developed a highly available kubernetes statefulset application , utilizing a single source with multiple replicas to ensure fault tolerance , scalability , and continuos service availability

## Major Components

### 1. Persistent Volume & Persistent Volume Claim Template
- Provides persistent storage for stateful applications.
- Ensures data persistence even if pods are deleted or recreated.
- Uses a Persistent Volume Claim (PVC) to automatically request and bind to the required storage resources.

### 2. Headless Service
- Used to maintain a consistent network identity for each pod.
- Does not assign an IP to the service but provides DNS entries for individual pods, allowing direct access to them.

### 3. StatefulSet
- Manages the deployment, scaling, and ordering of pods in the Kubernetes cluster.
- Ensures each pod has a unique and stable network identity.
- Handles pod scaling and failover, preserving the state across replicas.

### 4. HAProxy as Load Balancer
- Acts as a load balancer to distribute traffic evenly across the replicas.
- Ensures high availability by directing traffic to healthy pods.
- Provides a single entry point for external access to the application.

## Persistent Volume & Persistent Volume Claim Template
![Architecture Diagram](.\assets\volume\pv.png)
