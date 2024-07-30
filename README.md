# Load Balancer Setup with Ansible for Apache and PHP on EC2 Instances

This project automates the setup of a load balancer and deployment of a web server (Apache) with PHP on three EC2 instances using Ansible. The setup includes copying an `index.html` file to each server and configuring the load balancer to distribute traffic.


## Prerequisites

- Ansible 2.9 or later
- An inventory file with the IP addresses of the EC2 instances
- SSH access to the EC2 instances
- A suitable user with sudo privileges on the target servers
- A `index.html` file to be deployed

## Playbooks Overview

- **main.yml**: This is the main playbook that installs Apache, PHP, and configures the load balancer. It performs tasks such as:
  - Installing Apache and PHP on all EC2 instances
  - Copying `index.html` to `/var/www/html/` on each instance
  - Setting up and configuring the load balancer
  
- **Group Vars**: Group variables are used to manage configuration settings for different groups of servers. This allows for centralized management of variables such as server-specific settings, installation parameters, and load balancer configurations. Group Vars are defined in the `group_vars/` directory and are utilized in the playbook to ensure consistent and flexible configuration across the EC2 instances.