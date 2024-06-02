## Yolo Project Docker Setup Explanation

This repository contains the Docker setup for the Yolo project, consisting of both frontend and backend components. Below is an explanation of the Docker setup for this project:

## Choice of Base Image:
For the backend container, we opted for the node:14-slim base image, providing a lightweight Node.js environment.
Similarly, for the frontend container, we also used the node:14-slim base image to ensure consistency across environments.
## Dockerfile Directives:
## Backend Dockerfile:

1. Sets the working directory to /app.

2. Copies package.json and package-lock.json to the working directory.

3. Installs npm dependencies using npm install.

4. Copies the rest of the application files.

5. Exposes port 5000.

6. Defines the command to run the application (CMD ["node", "server.js"]).

## Frontend Dockerfile:

1. Sets the working directory to /app.
2. Copies package.json and package-lock.json to the working directory.
3. Installs npm dependencies using npm install.
4. Copies necessary files for the application.
5. Exposes port 3000.
6. Defines the command to run the application (CMD ["npm", "start"]).

## Docker-compose Networking:

1. Docker Compose automatically allocates ports for the containers based on the configuration in the docker-compose.yaml file.

2. Additional network configurations can be specified in the docker-compose.yaml file if required.
   Docker-compose Volume Definition and Usage:

        These volumes can then be mounted to specific paths within the containers as needed.
        Volumes can be defined in the docker-compose.yaml file in the root directory of yolo project. This is for the persistent data storage and communication between frontend and the backend.


## Git Workflow:

We followed standard Git workflow practices, including committing changes with descriptive messages, and 
pushing changes to the remote repository.

## procedures:
1. 'Git add .'
2. 'git commit -m "detailed descriptive"'
3. 'git push origin master'

## Successful Running of Applications:

The applications were tested locally to ensure they run successfully using Docker containers.
Debugging measures, such as checking logs (docker logs <container_name>) and verifying Dockerfile configurations, were applied if any issues occurred during the setup or running of the containers.

## Docker Image Tag Naming Standards:
Docker images were tagged using a versioning scheme (<repository>:<version>), where the version indicates the specific version of the application.
This helps in identifying different versions of images and containers easily.

## Screenshot of Deployed Image on DockerHub:
A screenshot of the deployed image on DockerHub, clearly showing the version of the image, is provided for reference and documentation purposes.

# Stage One: Ansible Instrumentation Explanation

This document provides an explanation of the setup and configuration implemented in Stage One of the project.

## Vagrant Configuration

We use Vagrant to create a virtual machine with an Ubuntu server for our development environment. The `Vagrantfile` contains the configuration settings for the virtual machine.

## Ansible Configuration

Ansible is used for server configuration and application deployment. The `ansible.cfg` file specifies Ansible configuration settings, and the `playbook.yaml` file defines the tasks to be executed.

## Ansible Roles

The tasks are organized into roles located in the `roles` directory. Each role represents a specific component of our system, such as installing packages or configuring services.

## Variables

Variable files in the `vars` directory are used to store variables that can be referenced in our Ansible playbook. This allows for greater flexibility and customization of our configuration.

# Stage Two: Kubernetes Instrumentation Explanation
This document provides an explanation of the setup and configuration implemented in Stage two of the project.

## Minikube 
Ensure Minikube is installed and configured properly on your local machine.

## kubectl
Ensure kubectl is installed and configured to interact with your Minikube cluster.

## namespace
Defines a separate namespace to isolate resources.

## Steps to Deploy on Kubernetes
1. Start Minikube 
   Start Minikube to spin the pod and clusters:

2. Apply Kubernetes Manifests
   Apply the Kubernetes manifests to create the necessary resources:
3. Port Conflicts
  Ensure no other services are using the ports required by Minikube. You can kill processes using the conflicting ports:
 
4.Container Runtime Issues
Ensure Docker or the container runtime is running:

 5. Deploying code on Cloud cluster
Install and Configure Google Cloud SDK:
Ensure you have the Google Cloud SDK installed and configured. Authenticate with your Google:


6.Cloud account and set the project
Create a GKE Cluster:
Create a GKE cluster to host your application:
Get Cluster Credentials:
Get the credentials for your GKE cluster to interact with it using kubectl:

6.Deploy Application on GKE
Apply the Kubernetes manifests to create the necessary resources on GKE:

7. Accessing the Application

Once deployed, you can access your application using the external IP address of the services. This can be found in the README.MD file with external IP URL:

