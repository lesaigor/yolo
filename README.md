# Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) 
- npm 
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) and start the mongodb service with `sudo service mongod start`

## Navigate to the Client Folder 
 `cd client`

## Run the folllowing command to install the dependencies 
 `npm install`

## Run the folllowing to start the app
 `npm start`

## Open a new terminal and run the same commands in the backend folder
 `cd ../backend`

 `npm install`

 `npm start`

 ### Go ahead a nd add a product (note that the price field only takes a numeric input)

 # Stage One: Ansible Instrumentation

This stage implements Ansible for server configuration and application deployment. It sets up a development environment using Vagrant with an Ubuntu server and provisions the necessary resources for running a web application.

## Project Structure

── ansible.cfg
├── playbook.yaml
├── roles
│ └── (Ansible roles)
└── vars
└── (Variable files)


- `ansible.cfg`: Ansible configuration file.
- `playbook.yaml`: Main Ansible playbook.
- `roles`: Directory containing Ansible roles for configuring different components.
- `vars`: Directory containing variable files used in the playbook.

## Running the Playbook

1. Make sure you have Ansible and Vagrant installed on your system.
2. Navigate to the project directory.
3. Run `vagrant up` to spin up the virtual machine.
4. Run `ansible-playbook playbook.yaml` to execute the Ansible playbook.

## Stage Two: Kubernetes Deployment

This stage deploys the application on a Kubernetes cluster. Initially, it can be tested on Minikube for local testing and then transitioned to AWS EKS for production deployment.

## Project Structure

── k8s-manifests
├── backend-deployment.yaml
├── backend-service.yaml
├── client-deployment.yaml
├── client-service.yaml
├── mongo-statefulset.yaml
├── mongo-service.yaml
└── namespace.yaml

### Minikube Setup (Local Testing)

1. Start Minikube:
    ```sh
    minikube start
    ```
2. Apply the Kubernetes manifests:
    ```sh
    kubectl apply -f k8s-manifests/namespace.yaml
    kubectl apply -f k8s-manifests/mongo-statefulset.yaml
    kubectl apply -f k8s-manifests/mongo-service.yaml
    kubectl apply -f k8s-manifests/backend-deployment.yaml
    kubectl apply -f k8s-manifests/backend-service.yaml
    kubectl apply -f k8s-manifests/client-deployment.yaml
    kubectl apply -f k8s-manifests/client-service.yaml
    ```
3. Verify the deployment:
    ```sh
    kubectl get pods -n yolo
    ```
4. Access the client service:
    ```sh
    minikube service client-service -n yolo
    ```

### AWS EKS Setup (Production)

1. Set up EKS cluster using eksctl:
    ```sh
    eksctl create cluster --name yolo-cluster --region <your-region> --nodegroup-name standard-workers --node-type t3.medium --nodes 3 --nodes-min 1 --nodes-max 4 --managed
    ```
2. Configure kubectl to use your EKS cluster:
    ```sh
    aws eks --region <your-region> update-kubeconfig --name yolo-cluster
    ```
3. Apply the same manifests to EKS:
    ```sh
    kubectl apply -f k8s-manifests/namespace.yaml
    kubectl apply -f k8s-manifests/mongo-statefulset.yaml
    kubectl apply -f k8s-manifests/mongo-service.yaml
    kubectl apply -f k8s-manifests/backend-deployment.yaml
    kubectl apply -f k8s-manifests/backend-service.yaml
    kubectl apply -f k8s-manifests/client-deployment.yaml
    kubectl apply -f k8s-manifests/client-service.yaml
    ```

## Accessing the app external
You can access the app using this link: https://13.56.77.16:3000/


## Explanation
For a detailed explanation of the project setup and configuration, refer to the `explanation.md` file.

##Author
Lesaigor Pride