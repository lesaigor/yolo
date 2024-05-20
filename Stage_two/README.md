# Stage 2: Ansible and Terraform Integration

This project extends the functionality of Stage 1 by integrating Terraform for resource provisioning alongside Ansible for server configuration and application deployment.


- `ansible.cfg`: Ansible configuration file.
- `playbook.yaml`: Main Ansible playbook.
- `roles`: Directory containing Ansible roles for configuring different components.
- `Terraform`: Directory containing Terraform configuration files for provisioning resources.
- `vars`: Directory containing variable files used in the playbook.

## Running the Integration

1. Ensure you have Ansible, Terraform, and Vagrant installed on your system.
2. Navigate to the project directory.
3. Use Vagrant to spin up the virtual machine (`vagrant up`).
4. Use Terraform to provision resources (`terraform init`, `terraform plan`, `terraform apply`).
5. Execute the Ansible playbook to configure the provisioned resources (`ansible-playbook playbook.yaml`).

## Explanation

For a detailed explanation of the integration and configuration, refer to the `explanation.md` file.


