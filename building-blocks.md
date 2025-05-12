I should be able to answer the following


what is object model


building blocks, nodes, namespaces, pods, replicasets, deployments, daemonsets


discuss labels and selectors


Each Node is managed by a  kubeltk  

Namespaces
    virtual sub-clusters called namespaces

    -- kubectl get namespaces
        This is used to list the namespaces
    -- kubectl create namespace new-namespace-name


pods
    - smallest workload object, 
    - represet a single instance of application
    - logical collection o fone or more containers, enclosing and isolating them to ensure
            - scheduled together
            - share network namespace
            - access to mount the same external storage
    - can't self heal
    - used together with controllers/ operators - fault-tolerance, self-healing


-- comands for pods
    kubectl get pods
    kubectl run firstrun --nginx-p

Nodes
    - Placing container into pods to run on Nodes.
    - Each Node is managed by control plane, 
    - can have several nodes in cluster
    - components - kubelets, container runtime, kube-proxy

// this is how to create a node in 
{
  "kind": "Node",
  "apiVersion": "v1",
  "metadata": {
    "name": "10.240.79.157",
    "labels": {
      "name": "my-first-k8s-node"
    }
  }
}


label-selectors


ReplicationControllers

-- ensures a specified number of replicas of pod are running at a given time    
    compares actual state and desired start are managed application
the recommended controller is ##deployments##

## deployments
    manages set of pods to run an application
    provide updates for pods and replicasets

    - create a deployment rollout
    - declare new state of pods
    - rollback to an earlier
    - scall up 
    - use the status of deployment
    - clean up older replicasets

Writing a deployment sets

    1. apiVersion --> 
    2. Kind
    3. metadata 

    4. Replicas, 
    5. strategy - used to replace old with new replicas
    6. recreate deployment  - spec.strategy.type == recreate, replaces all pods with ne

Daemonsets
- operators designed to manage node agents
    used in cases when we need to collect, monitor data from all nodes, run storage, networking, or proxy daemons on all nodes
    
