---

### **Create Pod Using YAML**

`pod.yaml`

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod-1
  labels:
    app: nginx
spec:
  containers:
  - name: cont-1
    image: nginx
    ports:
    - containerPort: 80
```

**Apply the file**

```bash
kubectl apply -f pod.yaml
```
