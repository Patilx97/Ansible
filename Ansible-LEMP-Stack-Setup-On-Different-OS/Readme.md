# Setting Up a LEMP Stack Using Ansible on Different OS
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a different OS using an Ansible playbook.  Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

## Steps
1. Create two EC2 Instances - a. Amazon linux b. Ubuntu  
2. Install Ansible in your system. If linux then ``` sudo apt-get install ansible -y ```
3. Clone this repository and navigate to the "Ansible-LEMP-Stack-Setup-On-Different-OS" directory.

```plaintext
   Ansible
    └── Ansible-LEMP-Stack-Setup-On-Different-OS
        ├── playbook.yml
        ├── README.md
        └── hosts.ini
```
Comments have been added in the playbook.yml and hosts.ini files explaining the use of each block.

4. Run the playbook (playbook.yml) : 
```bash
ansible-playbook -i hosts.ini playbook.yml
```
This command tells Ansible to use the **hosts.ini** inventory file and execute the tasks defined in the **playbook.yml** playbook.
