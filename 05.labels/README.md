# Labels

Labels are key value pairs that can be attached to objects (like tags in AWS)

Once labels are attached to an object, you can use filters to narrow down results. This is called **Label Selectors**

Using Label Selectors, you can use matching expressions to match labels

## Node Labels

You can use labels to tag nodes. Once nodes are tagged, you can use label selectors to let pods only run on specific nodes

For doing this you must first:
* tag the node
```
kubectl label nodes node1 hardware=high-spec
```
* then add a **nodeSelector** to your pod configuration
```
spec:
  ...
  nodeSelector:
    hardware: high-spec
```



## Code

```
# Start service
kubectl create -f 05.labels/helloworld-nodeselector.yml

# The pods are not up yet
kubectl get deployments
kubectl get pods

# If I describe the pod, there is an error to start the pod
kubectl describe pod helloworld-deployment-cb6fd95b9-9v5ht

# Add tag to minikube node 
kubectl label nodes minikube hardware=high-spec

# Check if label is up
kubectl get nodes --show-labels

# Now deployments and pods are up

```
