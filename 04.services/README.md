# Services

Creating a service will create an endpoint for your pod:
* a ClusterIP: a virtual IP address only reachable from within the cluster (this is the default)
* a NodePort: a port that is the same on each node that is also reachable externally
* a LoadBalancer: a LoadBalancer created by the cloud provider that will route external traffic to every node on the NodePort  

There is also the possibility to create DNSs names
* ExternalName can provide a DNS name for the service
* This only works when the DNS add-on is enabled 


```
# Create example 
kubectl create -f 04.services/helloworld.yml

# Describe pod
kubectl describe pod nodehelloworld.example.com

# Create nodeport service
kubectl create -f 04.services/helloworld-nodeport-service.yml 

# Get url 
minikube service helloworld-service --url

```