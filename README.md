# Kubernetes-CheatSheet
## Cluster Introspection

List all services:

    kubectl get services   
    
List all pods

    kubectl get pods 
    
Watch nodes continuously

    kubectl get nodes -w   

Get version information

    kubectl version                     

Get cluster information

    kubectl cluster-info  

Get the configuration

    kubectl config view   
    
Output information about a node

    kubectl describe node <node>        

## Pod and Container Introspection

List the current pods

        kubectl get pods 

Describe pod <name>
    
        kubectl describe pod <name>              

List the replication controllers

        kubectl get rc  
        
List the replication controllers in <namespace>
    
        kubectl get rc --namespace="<namespace>" 

Describe replication controller <name>
    
        kubectl describe rc <name>               

List the services

        kubectl get svc  

Describe service <name>
    
        kubectl describe svc <name>              

## Interacting with Pods

Launch a pod called <name>
using image <image-name>
    
        kubectl run <name> --image=<image-name>                              
                                                                    
 
kubectl create -f <manifest.yaml>                                   # Create a service described 
                                                                    # in <manifest.yaml>
 
kubectl scale --replicas=<count> rc <name>                          # Scale replication controller 
                                                                    # <name> to <count> instances
 
kubectl expose rc <name> --port=<external> --target-port=<internal> # Map port <external> to 
                                                                    # port <internal> on replication 
                                                                    # controller <name>


## Stopping Kubernetes

kubectl delete pod <name>                                         # Delete pod <name>
kubectl delete rc <name>                                          # Delete replication controller <name>
kubectl delete svc <name>                                         # Delete service <name>
kubectl drain <n> --delete-local-data --force --ignore-daemonsets # Stop all pods on <n>
kubectl delete node <name>                                        # Remove <node> from the cluster

kubectl delete pod <name>                                         # Delete pod <name>
kubectl delete rc <name>                                          # Delete replication controller <name>
kubectl delete svc <name>                                         # Delete service <name>
kubectl drain <n> --delete-local-data --force --ignore-daemonsets # Stop all pods on <n>
kubectl delete node <name>   # Remove <node> from the cluster

## Debugging
kubectl exec <service> <command> [-c <$container>] # execute <command> on <service>, optionally 
                                                   # selecting container <$container>

kubectl logs -f <name> [-c <$container>]           # Get logs from service <name>, optionally
                                                   # selecting container <$container>

watch -n 2 cat /var/log/kublet.log                 # Watch the Kublet logs
kubectl top node                                   # Show metrics for nodes
kubectl top pod                                    # Show metrics for pods


Administration
kubeadm init                                              # Initialize your master node
kubeadm join --token <token> <master-ip>:<master-port>    # Join a node to your Kubernetes cluster
kubectl create namespace <namespace>                      # Create namespace <name>
kubectl taint nodes --all node-role.kubernetes.io/master- # Allow Kubernetes master nodes to run pods
kubeadm reset                                             # Reset current state

kubectl get secrets                                       # List all secrets
kubeadm init                                              # Initialize your master node
kubeadm join --token <token> <master-ip>:<master-port>    # Join a node to your Kubernetes cluster
kubectl create namespace <namespace>                      # Create namespace <name>
kubectl taint nodes --all node-role.kubernetes.io/master- # Allow Kubernetes master nodes to run pods
kubeadm reset                                             # Reset current state
 
kubectl get secrets                                       # List all secrets


kubectl exec <service> <command> [-c <$container>] # execute <command> on <service>, optionally 
                                                   # selecting container <$container>
 
kubectl logs -f <name> [-c <$container>]           # Get logs from service <name>, optionally
                                                   # selecting container <$container>
 
watch -n 2 cat /var/log/kublet.log                 # Watch the Kublet logs
kubectl top node                                   # Show metrics for nodes
kubectl top pod                                    # Show metrics for pods
