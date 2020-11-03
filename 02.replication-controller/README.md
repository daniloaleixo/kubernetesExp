
## Replication Controller

* The replication controller will ensure a specified number of pods replicas will run at all time
* Pods created with the replica controller will automatically be replaced if they fail, get deleted or are terminated
* Using the replication controller is also recommended if you just want to make sure 1 pod is always running, even after reboots 



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