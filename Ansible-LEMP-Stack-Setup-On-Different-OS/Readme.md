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
 cd Ansible/Ansible-LEMP-Stack-Setup-On-Different-OS/
```

4. Transfer the .pem Files
Ensure that the .pem files for the Amazon Linux and Ubuntu servers are present in the same directory where the hosts.ini and playbook.yml files are located.  These files are necessary for SSH access to the respective servers.

To transfer the .pem files from your local machine to the directory, use the scp command:

```bash
# Transfer the Amazon Linux .pem file
scp -i path_to_your_key.pem path_to_amazon-linux.pem ec2-user@public_ip:/path_to_Ansible-LEMP-Stack-Setup-On-Different-OS/

# Transfer the Ubuntu .pem file
scp -i path_to_your_key.pem path_to_ubuntu.pem ubuntu@public_ip:/path_to_Ansible-LEMP-Stack-Setup-On-Different-OS/
```

The directory structure should look like this:
```plaintextAnsible
 └── Ansible-LEMP-Stack-Setup-On-Different-OS
     ├── playbook.yml
     ├── README.md
     ├── hosts.ini
     ├── amazon-linux.pem
     └── ubuntu.pem
```
Comments have been added in the playbook.yml and hosts.ini files explaining the use of each block.

4. Run the playbook  

```bash
 ansible-playbook -i hosts.ini playbook.yml
```
This command tells Ansible to use the **hosts.ini** inventory file and execute the tasks defined in the **playbook.yml** playbook.
