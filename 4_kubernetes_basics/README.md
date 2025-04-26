# L18-04

Let's deploy an Nginx container using both methods.

## Imperative

    kubectl create deployment mynginx1 --image=nginx
    kubectl get deployment

## Declarative

    kubectl create -f deploy-1.yaml
    kubectl get deployment

## Cleanup

    kubectl delete deployment mynginx1
    kubectl delete deploy mynginx2