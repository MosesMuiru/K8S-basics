## Authentication, Authorization, Admission Control


# Authentication

kubernetes has two kind of users
    Normal Users
    - managed outsides of k8s clusters
    Service Accounts
    - tied to a particular namespace

- allows anonymous request, user impresonation


# Authorization
    1. Node
    authorizes apis request made by kubelets

    2. Attribute-Based Access Control(ABAC)
    grantes access to api requests
    from policies, a user can be restricted
    
    {
  "apiVersion": "abac.authorization.kubernetes.io/v1beta1",
  "kind": "Policy",
  "spec": {
    "user": "bob",
    "namespace": "lfs158",
    "resource": "pods",
    "readonly": true
    }
    }

    3. webhook
    4. Role Based Access Control(RBAC)



