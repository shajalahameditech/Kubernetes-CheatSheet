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
