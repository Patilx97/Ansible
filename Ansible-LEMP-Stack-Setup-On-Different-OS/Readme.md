# Setting Up a LEMP Stack Using Ansible on Different OS
## Introduction
In this guide, we will walk through the steps to set up a LEMP stack (Linux, Nginx, MySQL, PHP) on a different OS using an Ansible playbook.  Ansible is a powerful automation tool that allows you to manage and configure systems at scale.

## Steps
1. Create two EC2 Instances  
    Amazon linux  
    Ubuntu
   
2. Install Ansible on Your System  
If you are using a Linux system, install Ansible with the following command:
   
```bash
 sudo apt-get install ansible -y
```

3. Clone the Repository  
Clone this repository and navigate to the Ansible-LEMP-Stack-Setup-On-Different-OS directory:
```bash
 git clone <repository-url>
 cd Ansible-LEMP-Stack-Setup-On-Different-OS
```
   
The directory structure should look like this:
```plaintext
 Ansible-LEMP-Stack-Setup-On-Different-OS
 ├── playbook.yml
 ├── README.md
 └── hosts.ini
```
Comments have been added in the playbook.yml and hosts.ini files explaining the use of each block.

5. Run the playbook (playbook.yml) :  

```bash
 ansible-playbook -i hosts.ini playbook.yml
```
This command tells Ansible to use the **hosts.ini** inventory file and execute the tasks defined in the **playbook.yml** playbook.
