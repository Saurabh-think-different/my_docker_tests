# Learning about kubectl, contexts, namespaces

kubectl = CLI for interacting with K8s API

    kubectl config get-contexts
    kubectl config current-context
    kubectl config use-context [context]
    kubectl get ns
    kubectl create ns [namespace]
    kubectl delete ns [namespace]
    kubectl get pods --all-namespaces

Let's deploy an Nginx container using both methods.

### Imperative

    kubectl create deployment mynginx1 --image=nginx
    kubectl get deployment

### Declarative

    kubectl create -f deploy-1.yaml
    kubectl get deployment

### Cleanup

    kubectl delete deployment mynginx1
    kubectl delete deploy mynginx2



question | Context | Namespace |
| ----------- | -------------- | ------------------------- |
What it is | A profile that chooses a cluster, a user, and optionally a namespace | A virtual separation inside a cluster to organize resources |
Scope | "Which cluster am I talking to, as which user, and in which namespace (by default)?" | "Which folder am I working in inside the cluster?" |
Location | Exists inside your local kubeconfig file (~/.kube/config) | Exists inside the cluster as part of Kubernetes itself |
Example | prod-context might point to the Production cluster with admin user and namespace prod | prod namespace contains Prod deployment pods, different from dev namespace |