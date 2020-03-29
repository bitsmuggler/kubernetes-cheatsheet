# kubernetes-cheatsheet

## kubectl
Commandline client for accessing Kubernetes master node endpoint

| Description        | Command  |
| ------------- |-------------|
| Starts a local proxy to access the kubernetes api | `kubectl proxy` |
| Get an access token | `kubectl describe secret -n kube-system $(kubectl get secrets -n kube-system | grep default  cut -f1 -d ' ') | grep -E '^token' | cut -f2 -d':' | tr -d '\t' | tr -d " "`|
| Get API server endpoint(s) | `kubectl config view | grep https | cut -f 2- -d ":" | tr -d " "`|
| Get Cluster info | `kubectl cluster-info`
| List namespaces | `kubectl get namespaces`
| Create a deployment | `kubectl create deployment test-nginx --image=nginx:1.17.9-alpine`
| Get deployments, ReplicaSets and Pods (shortnames)| `kubectl get deploy,rs,po`
| Get deployments, ReplicaSets and Pods (shortnames) with a specific label | `kubectl get deploy,rs,po -l app=test-nginx`
| Scale the deployment up to 3 replicas| `kubectl scale deploy test-nginx --replicas=3`
| Show deplyoment configuration| `kubectl describe deployment test-nginx`
| Show rollout history of a deployment | `kubectl rollout history deploy test-nginx`
| Show details of a specific revision entry| `kubectl rollout history deploy test-nginx --revision=1`
| Set a image on a deployment|`kubectl set image deploy test-nginx nginx=nginx:1.16-alpine`
| Rollback a deployment to a past revision| `kubectl rollout undo deployment test-nginx --to-revision=1`
| Show kubectl client configuration file| `kubectl config view`
| Create namespace| `kubectl create namespace test-namespace`
| Create object from filename| `kubectl create -f test-file.yml


## minikube

Tool for starting kubernetes locally (All-in one single node installation)

| Description        | Command  |
| ------------- |-------------|
| Start minikube (Kubernetes locally) | `minikube start` |
| Show dashboard |`minikube dashboard`|

