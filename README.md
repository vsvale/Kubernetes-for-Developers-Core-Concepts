# [Kubernetes for Developers: Core Concepts](https://app.pluralsight.com/library/courses/kubernetes-developers-core-concepts)
Do you need to learn core Kubernetes concepts in order to get your application containers running in a cluster? This course provides a developer-focused look at key Kubernetes resources, benefits they can provide, and how to get started using them.

## Description
If you need to get your application containers into Kubernetes, then this course will help jumpstart that process. In this course, Kubernetes for Developers: Core Concepts, you'll be provided a developer-focused look at the role Kubernetes can play in the development workflow. First, you'll learn how to get Kubernetes up and running locally on your machine, interact with Kubernetes using kubectl, and how to use different resources it provides. Next, you'll discover how to deploy containers within Pods, work with deployments, and expose a Pod with a service. Then, you'll explore the role of storage, ConfigMaps, and secrets. Finally, you'll delve into troubleshooting Pods. By the end of this course, you'll understand the role Kubernetes can play in your development workflow and how it can be used to orchestrate and manage your containers. 

## Author
[Dan Wahlin](https://app.pluralsight.com/profile/author/dan-wahlin)

## Platform
[Pluralsight](pluralsight.com/)

## Notes
- kubectl version: check k8s version
- kubectl cluster-info: view cluster info
- kubectl get all: retrieve info about k8s pods, deployments, services and more
    - kubectl get pods: list pods
    - kubectl get pod my-nginx -oyaml
- kubect run container-name --image=image-name: create a pod imperatively
    - kubectl run my-ngnix --image=nginx:alpine
- kubectl port-forward pod ports: foward a port to allow external access
    - kubectl port-forward my-nginx 8080:80
- kubectl create resource: create a resource imperatively
    - kubectl create -f https://raw.githubusercontent.com/vsvale/Kubernetes-for-Developers-Core-Concepts/main/nginx.pod.yml --dry-run --validate=true --save-config
- kubectl apply resource: create a resource declaratively
    - kubectl create -f https://raw.githubusercontent.com/vsvale/Kubernetes-for-Developers-Core-Concepts/main/nginx.pod.yml
    - kubectl delete -f https://raw.githubusercontent.com/vsvale/Kubernetes-for-Developers-Core-Concepts/main/nginx.pod.yml
- kubectl describe pod podname: show status and erros in pod
- Deployment: kubectl appply -f deployment.yaml
    - kubectl get deployments --show-labels
    - kubectl get deployments -l app=nginx
    - kubectl delete deployment name-dployment: delete deployment that manages the Pod
    - kubectl scale deployment deployment-name --replicas=5
- Services:
    - kubectl port-foward pod/my-nginx
    - kubectl port-foward deployment/my-nginx 8080
    - kubectl apply -f clusterip-service.yaml
    - kubectl apply -f nodeport.yaml
    - kubectl apply -f loadbalancer.yaml
- Volumes:
    - kubectl apply -f mongodb.yaml
- ConfigMap
    - kubectl get cm configmap-name -oyaml
    - kubectl apply -f congifmap.yaml
    - kubectl create cm app-sttings --from-env-file=settings.config
- Logs
    - kubectl logs -f podname
- Shell
    - kubectl exec poname -it sh
