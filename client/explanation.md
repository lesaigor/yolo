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

##