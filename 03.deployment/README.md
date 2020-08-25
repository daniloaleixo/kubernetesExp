### Replication Set

- Replica Set is the next gen Replication Controller
- It Supports a new selector that can do selection based on filtering according a set of values (environment either "dev" or "qa")
- The Replica Set is used by the deployment (Replication Controller dont)

### Deployment 
- When using the deployment object, you define the **state** of your application and kubernetes will then make sure the clusters matches your desired state
- With a deployment object you can:
  - Create a deployment (Ex: Deploy an app)
  - Update a deployment (Ex: Deploy a new version)
  - Do rolling updates
  - Roll back to a previos version
  - Pause or resume the deployment

```
# Useful commands
kubectl get deployments
kubectl get rs # Get info about replica sets
kubectl get pods # Show pods running
kubectl rollout status <name_deployment> # get deployment status
kubectl set image <name_deployment> k8s-demo=<new_image_name> # set a new image
kubectl edit <name_deployment> # Edit deployment
kubectl rollout history <name_deployment> # Get the rollout history
kubectl rollout undo <name_deployment> --to-revision=n # Rollout to a previos version


# Running 
kubectl create -f 03.deployment/helloworld-deployment.yml
kubectl get deployments
kubectl get rs
kubectl get pods --show-labels

# Exposing service 
kubectl expose deployment helloworld-deployment --type=NodePort --port=8080
kubectl get service
kubectl describe service helloworld-deployment
minikube service helloworld-deployment --url

# Clean up
kubectl delete service/helloworld-deployment
kubectl delete deployment/helloworld-deployment
```