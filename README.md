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

## Explanation

For a detailed explanation of the project setup and configuration, refer to the `explanation.md` file.
