    kubectl get service, endpointes frontend-svc
or
    kubectl get svc, ep frontend-svc



----
## Kube-Proxy
is a node-agent that watches the api server on control plane node for addition, updates, removal services and endpoints
implements the service configuration

iptables rules to capture the traffic its clusterIP


traffic policies

allow users to instruct kube-proxy on context of traffic routig, 
    cluster
    local

    1. Cluster
        allow to tartget all ready endpointes services in the load balancing process
    2. Local option
        load balancing process to include only endpoints of services located in the saem node as the requester pod


## Service Discovery
    two methods of discovery
    1. Environment variables
    2. DNS


Service Type
    clusterIP - this is the virtualIP address 
    used for communicating with the service and accessible only from withing the cluster


## LoadBalancer


