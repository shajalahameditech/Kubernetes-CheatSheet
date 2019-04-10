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
