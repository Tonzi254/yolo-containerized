# Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04). This will be installed on the frontend and backend containers on the Kubernetes cluster from a pre-compiled Docker Hub image on my repository
- [npm]. This will be installed on the frontend and backend containers on the Kubernetes cluster from a pre-compiled Docker Hub image on my repository
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) and start the mongodb service with `sudo service mongod start`. This should be installed on the database container on the Kubernetes cluster from a Docker Hub image
- [Kubernetes]. This should be installed on your local machine or cloud environment by installing Minikube and Kubectl tools. To start the Kubernetes cluster and create the containers

## Open the terminal and start Kubernetes
`minikube start`

## Clone my Github repo to your machine the application root directory and open the client folder 
 `git clone https://github.com/Tonzi254/yolo-containerized.git yolo-orchestration`

## Navigate to the database folder containing the MONGO DB installation scripts 
 `cd ./yolo-orchestration/database`

## Run the following commands to deploy the database container to Kubernetes
 `$ kubectl create -f deployment.yaml && kubectl create -f configMap.yaml && kubectl create -f service.yaml && kubectl create -f mongo-pv.yaml && kubectl create -f mongo-pvc.yaml && kubectl apply -f deployment.yaml`

## Navigate to the backend folder containing the backend application 
 `cd ./yolo-orchestration/backend`

## Run the following commands to deploy the backend container to Kubernetes
 `$ kubectl create -f deployment.yaml && kubectl create -f configMap.yaml && kubectl create -f service.yaml && kubectl apply -f deployment.yaml`

## Navigate to the client folder containing the frontend application
 `cd ./yolo-orchestration/client`

## Run the following commands to deploy the frontend container to Kubernetes
 `$ kubectl create -f deployment.yaml && kubectl create -f configMap.yaml && kubectl create -f service.yaml && kubectl apply -f deployment.yaml`

### Go ahead and open another terminal and enter the command `minikube dashboard` to view and manage the deployments and stateful set for the Kubernetes cluster you have created)