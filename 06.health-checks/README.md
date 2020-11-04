# Health Check

You can run 2 different type of health check;
* running a command in the container periodically
* Periodic checks a URL (http)

Example:
```
kind: Pod
spec:
  containers:
    ...
    livenessProbe:
      httpGet:
        path: /
        port: 3000
      initialDelaySeconds: 15
      timeoutSeconds: 30
```

## Code
```

kubectl create -f 06.health-checks/helloworld-healthcheck.yml

# Get pods
kubectl get pods

# It will have liveness line which will describe the health check 
kubectl describe pod helloworld-deployment-5b7d8b4985-6jz7x

```