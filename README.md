# Ansible Playbook for Nexus Deployment with Tearraform

This repository contains automation scripts and configurations for deploying a Nexus repository manager using Ansible and Terraform.

## Directory Structure

- **terraform-ec2**: Terraform configuration directory for provisioning AWS resources.
    - **main.tf**: Terraform configuration file defining AWS resources like VPC, subnets, security groups, and EC2 instances.
    - **terraform.tfvars**: Terraform variables file containing configuration parameters such as VPC CIDR block, subnet CIDR block, etc.
- **ansible.cfg**: Ansible configuration file specifying settings like inventory and remote user.
- **hosts**: Ansible inventory file specifying Nexus server IP address and SSH key location.
- **deploy-nexus.yaml**: Ansible playbook for installing and configuring Nexus repository manager.
- **commands-for-manual-installation.sh**: Shell script containing manual installation steps for Nexus.

## Usage

1. **Terraform Configuration**:
   - Navigate to the `terraform-ec2` directory.
   - Update the `terraform.tfvars` file with desired configurations.
   - Run `terraform init`, `terraform plan`, and `terraform apply` to provision EC2 instance on AWS.

2. **Ansible Configuration**:
   - Update `ansible.cfg` with necessary settings.
   - Ensure that the inventory file `hosts` contains correct Nexus server information.
   - Adjust the playbook `deploy-nexus.yaml` if needed for custom configurations.

3. **Deploy Nexus Repository Manager**:
   - Execute the Ansible playbook `deploy-nexus.yaml` to install and configure Nexus on the provisioned EC2 instance.
   - Verify Nexus installation and configuration using the provided tasks.

4. **Manual Installation (Optional)**:
   - If needed, you can use `commands-for-manual-installation.sh.sh` for manual Docker installation on servers.

## Notes
- This setup automates the deployment of Nexus repository manager on AWS infrastructure using Ansible and Terraform.
- Ensure proper AWS credentials are configured for Terraform to provision resources.
- Customize the Terraform and Ansible configurations according to your infrastructure and deployment requirements.
- Review and modify shell scripts (`commands-for-manual-installation.sh`) before executing them in production environments.