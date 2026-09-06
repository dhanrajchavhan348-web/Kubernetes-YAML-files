---
### Kubernetes Service Types for Networking

#### 1. **ClusterIP**
- Default service type.
- Exposes the service only within the cluster.
- Example:
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-clip-svc
spec:
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
```

**Apply the file**

```bash
kubectl apply -f ClusterIP.yaml
```


#### 2. **NodePort**
- Exposes the service on a static port on each node.
- Example:
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-np-svc
spec:
  type: NodePort
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
    nodePort: 31195
```

**Apply the file**

```bash
kubectl apply -f NodePort.yaml
```


#### 3. **LoadBalancer**
- Exposes the service externally using a cloud provider’s load balancer.
- Example:
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-lb-service
spec:
  type: LoadBalancer
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
```

**Apply the file**

```bash
kubectl apply -f LoadBalancer.yaml
```


#### 3. **ExternalName**
 - Use ExternalName when you want a Kubernetes Service to point to an external service/DNS name.
  ```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-Exn-service
spec:
  type: ExternalName
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
```

**Apply the file**

```bash
kubectl apply -f ExternalName.yaml
``` 
