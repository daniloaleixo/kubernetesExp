### First Demo
```
minikube start

# Get cluster info
kubectl cluster-info

# Get nodes
kubectl get nodes



# Create deployment
kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4

# Get deployments
kubectl get deployments


# Create load balancer
kubectl expose deployment hello-node --type=LoadBalancer --port=8080

# Get services
kubectl get services

# TO check url
minikube service hello-node


# Clean up
kubectl delete service hello-node
kubectl delete deployment hello-node
```