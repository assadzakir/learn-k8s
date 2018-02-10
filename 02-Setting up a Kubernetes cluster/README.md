#Install Minikube

https://github.com/kubernetes/minikube

# Start a kubernetes cluster with minikube

$ minikube start

# Install the kubernetes client (KUBECTL)

https://kubernetes.io/docs/tasks/tools/install-kubectl/

# Displaying cluster information

$ kubectl cluster-info

# Creating a three-node cluster in GKE

$ gcloud container clusters create kubia --num-nodes 3
➥ --machine-type f1-micro

# Listing cluster nodes with kubectl

$ kubectl get nodes

# Retrieving additional details of an object

$ kubectl describe node nodeName

# Deploying your docker hub image

$ kubectl run kubia --image=assadzakir/kubia --port=8080 --generator=run/v1

# Listing pods

$ kubectl get pods

# Creating a service object

$ kubectl expose rc kubia --type=LoadBalancer --name kubia-http

# Listing Services

$ kubectl get services or svc

NOTE: Minikube doesn't support LoadBalancer services, so the service will never get an external IP.
But you can access ther service anyway through its external port. 

TIP:When using Minikube, you can get the IP and port through which you can access the service by
running minikube service kubia-http

# List Replication Controllers

$ kubectl get replicationcontrollers or rc

NOTE:Listing all the resource types with kubectl get command

# Increasing the desired replica count

$ kubectl scale rc kubia --replicas=3

# Displaying the pod ip and the pod's node when listing pods

$ kubectl get pods -o wide

# Describing a pod with kubectl describe

$ kubectl describe pod <podName>

# Accessing the dashboard when running kubernetes in GKE

$ kubectl cluster-info | grep dashboard

# Getting username and password for dashboard in GKE

$ gcloud container clusters describe kubia | grep -E "(username|password): 

# Accessing the dashboard when using minikube
$ minikube dashboard