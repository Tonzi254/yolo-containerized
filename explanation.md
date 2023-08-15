OBJECTIVES
# 1.Git Work Flow
After cloning the supplied repository to my local machine I did a git fetch and then set the remote origin to my repo url.
I changed directory to client and then created a Dockerfile for the frontend of the app and pushed it to the repo.
I changed directory to backend and created another Dockerfile for the backend of the app and pushed it to the repo.
I created the kubernetes yaml files for creating the deployment, services, config map, secrets for the three containers: frontend and backend
Finally I created a new directory for database and added yaml files for creating the statefulset deployment, services, config map, secrets, persistent volume and persistent volume claim

# 2.Image Tagging, Versioning and Personalization
The two images Yolo-Client and Yolo-Backend were versioned to 1:0:2 and 1.0.1 respectively following the smever conventions. The default latest image tag was not used so as to be able to distinguish between versions of the front end and backend apps during development. Mongo image was not versioned since it was being directly pulled from Docker Hub by Kubernetes during container creation. The images were also tagged with my Dockerhub username to allow for pushing and pulling to Docker Hub and easier identification of images that are on the remote repository.

# 3.Kubernetes Objects

1. Deployment YAML
These are script files used by Kubectl tool to create the frontend, backend and database deployments on the Kubernetes cluster

2. Service YAML
These are script files used by Kubectl tool to create connectivity between the frontend, backend and database services on the Kubernetes cluster and expose them externally without which the services would have no means of communication with each other and the user would not be able to access the pods outside of the Kubernetes environment

3. Config Map YAML
These are script files used by Kubectl tool to pass the environmental variables such as PORT numbers the frontend, backend and database containers on the Kubernetes cluster

4. Secret YAML
These are script files used by Kubectl tool to more securely pass the database credentials such as username, password and MONGO DB URI to the backend and database containers on the Kubernetes cluster

5. Persistent Volume and Persistent Volume Claim YAMLs
These are script files used by Kubectl tool to create a persistent storage volume and link the volume to the database application to use to store user data/input such that even when the containers are terminated and restarted again the user data isn't lost and once again becomes available.

6. Statefulset
This script was incorporated into the database deployment YAML script file to enable creation of a set of pods that are unique and persistent and with a stable pod name such that even with restarts the same pod name is retained each time.