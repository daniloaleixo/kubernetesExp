```
# Create replication controller
kubectl create -f ./02.replication-controller/helloworld-replicationController.yml
kubectl get pods

# Scale replication controller
kubectl get rc
kubectl scale --replicas=4 rc/nodehelloworld-controller

# Delete RC
kubectl delete rc/nodehelloworld-controller

```