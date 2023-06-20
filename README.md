EXPERIMENT: 8

Setup kubernetes with MiniKube on Ubuntu AWS Ec2 Instance
 
PORT NUMBER AS TCP :30000-32767 IPV4
PORT NUMBER AS TCP :30000-32767:IPV6

MiniKube

MiniKube used to Run the Kubernetes Locally.

Minikube is a single-node Kubernetes cluster that you can use locally in your own development machine to test your Kubernetes deployment scripts, explore and study Kubernetes etc.

MiniKube is used for Development Purposes.

Minikube can’t be used in Production, as It’s One Node Machine.

# Steps:-


// For Docker Installation
$ sudo apt-get update
$ sudo apt-get install docker.io -y
$ sudo usermod -aG docker $USER && newgrp docker
// For Minikube & Kubectl
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube

$ sudo snap install kubectl --classic
$ minikube start --driver=docker
// test the minikube status
$ minikube status
Check the minikube using kubectl:
$ kubectl get pods
$ kubectl get svc




EXPERIMENT :::9


$ kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4
$ kubectl expose deployment hello-node --type=NodePort --port=8080
$ kubectl get svc (USE PORT NUM )
Note also that we can access it within the cluster via $(minikube ip):$NODE_PORT::
$ minikube ip
$ curl 172.31.50.87:32256
$ minikube service hello-node
