
You must run either:

    minikube image load fastapi-ping
OR

    eval $(minikube docker-env)
    docker build -t fastapi-ping .

Otherwise Kubernetes will always fail to pull your local images to minikube(or just push it to docker hub repo: docker push saurabhdevs/myrepo:latest)

At last run this to go back to regular local docker images:

    eval $(minikube docker-env -u)

