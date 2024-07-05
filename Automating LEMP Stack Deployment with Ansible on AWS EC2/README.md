# Setting Up a LEMP Stack Using Ansible
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a remote server using an Ansible playbook. Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

Before we begin, ensure you have Ansible installed on your local machine.  
## Inventory File
The inventory file, **hosts.ini**, defines the remote server we will be configuring. Here is the content of the hosts.ini file:
```bash
[lemp_server]
Target_Server_Public_IP ansible_user=ubuntu ansible_ssh_private_key_file=./KEY_PAIR_NAME.pem
```
