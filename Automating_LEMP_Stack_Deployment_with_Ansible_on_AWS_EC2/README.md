# Setting Up a LEMP Stack Using Ansible on remote server
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a remote server using an Ansible playbook. Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

## Steps
1. Create 2 EC2 Ubuntu Instances
   ◦ Host instance
   ◦ Target instance

2. Connect to Host instance.
3. Clone this repository and navigate to this "Automating_LEMP_Stack_Deployment_with_Ansible_on_AWS_EC2" directory.

```plaintext
   Ansible
    └── Automating_LEMP_Stack_Deployment_with_Ansible_on_AWS_EC2
        ├── LEMP.yml
        ├── README.md
        └── hosts.ini
```
4. Now run the playbook (LEMP.yml) : 
```bash
ansible-playbook -i hosts.ini LEMP.yml
```
This command tells Ansible to use the **hosts.ini** inventory file and execute the tasks defined in the **LEMP.yml** playbook.
