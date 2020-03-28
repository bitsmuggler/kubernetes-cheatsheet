# kubernetes-cheatsheet

## kubectl
Commandline client for accessing Kubernetes master node endpoint

| Description        | Command  |
| ------------- |-------------|
| Starts a local proxy to access the kubernetes api | `kubectl proxy` |
| Get an access token | `TOKEN=$(kubectl describe secret -n kube-system $(kubectl get secrets -n kube-system | grep default | cut -f1 -d ' ') | grep -E '^token' | cut -f2 -d':' | tr -d '\t' | tr -d " ")`|
| Get API server endpoint(s) | `APISERVER=$(kubectl config view | grep https | cut -f 2- -d ":" | tr -d " ")`|
| Get Cluster info | `kubectl cluster-info`

## minikube

Tool for starting kubernetes locally (All-in one single node installation)

| Description        | Command  |
| ------------- |-------------|
| Start minikube (Kubernetes locally) | `minikube start` |
| Show dashboard |`minikube dashboard`|

