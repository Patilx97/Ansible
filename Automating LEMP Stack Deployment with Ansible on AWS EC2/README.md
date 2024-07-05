# Setting Up a LEMP Stack Using Ansible to remote server
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a remote server using an Ansible playbook. Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

Setup & Create EC2 UBUNTU target instance.

Before we begin, ensure you have Ansible installed on your local machine.  

Clone this repository to local machine, it is having following files:  
1. LEMP.yml
2. hosts.ini

Also Keep KEY_PAIR.pem file in same location.

## Inventory File
The inventory file, **hosts.ini** , defines the remote server we will be configuring.  
