# Setting Up a LEMP Stack Using Ansible on different OS
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a remote server using an Ansible playbook. Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

## Steps
1. Create 2 EC2 Ubuntu Instances
   ◦ Host instance
   ◦ Target instance

2. Connect to Host instance.
3. Clone the repository and navigate to the "Automating_LEMP_Stack_Deployment_with_Ansible_on_AWS_EC2" directory.

```plaintext
   Ansible
    └── Automating_LEMP_Stack_Deployment_with_Ansible_on_AWS_EC2
        ├── LEMP.yml
        ├── README.md
        └── hosts.ini
```
Comments have been added in the LEMP.yml and hosts.ini files explaining the use of each block.

4. Run the playbook (LEMP.yml) : 
```bash
ansible-playbook -i hosts.ini LEMP.yml
```
This command tells Ansible to use the **hosts.ini** inventory file and execute the tasks defined in the **LEMP.yml** playbook.
