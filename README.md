# Kubernetes-for-Developers-Core-Concepts

## Notes
- kubectl version: check k8s version
- kubectl cluster-info: view cluster info
- kubectl get all: retrieve info about k8s pods, deployments, services and more
    - kubectl get pods: list pods
- kubect run container-name --image=image-name: create a pod imperatively
    - kubectl run my-ngnix --image=nginx:alpine
- kubectl port-forward pod ports: foward a port to allow external access
    - kubectl port-forward my-nginx 8080:80
- kubectl create resource: create a resource imperatively
- kubectl apply resource: create a resource declaratively
- kubectl delete deployment name-dployment: delete deployment that manages the Pod
