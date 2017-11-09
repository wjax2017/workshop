# Kubernetes
## Install minikube and kubectl

### MacOS

`curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/`

`curl -LO  https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/`

### Linux

`curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/`

`curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/`

## Start a minikube cluster on MacOS

### Enable Heapster and Ingress

`minikube addons enable heapster; minikube addons enable ingress`

## Start a minikube cluster on Linux

`minikube start --memory=4096`

### Create cluster on MacOS

`minikube start --memory=8192 --vm-driver=xhyve`

### Create dashboard

`minikube service kubernetes-dashboard --namespace kube-system`

### Create Nginx proxy

`kubectl run nginx --image nginx --port 80`

### Expose the proxy

`kubectl expose deployment nginx --type NodePort --port 80`

### Open in browser

`minikube service nginx`
