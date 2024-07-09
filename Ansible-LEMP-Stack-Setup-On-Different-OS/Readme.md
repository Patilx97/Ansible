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

The output will look like this on terminal:

```bash
PLAY [Installing LEMP on remote servers having different OS] ******************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************
ok: [10.0.1.221]
ok: [10.0.1.182]

TASK [update package manager] *************************************************************************************************************************************
skipping: [10.0.1.221]
changed: [10.0.1.182]

TASK [update dnf] *************************************************************************************************************************************************
skipping: [10.0.1.182]
ok: [10.0.1.221]

TASK [install LEMP on ubuntu server] ******************************************************************************************************************************
skipping: [10.0.1.221] => (item=nginx) 
skipping: [10.0.1.221] => (item=php) 
skipping: [10.0.1.221] => (item=php8.3-fpm) 
skipping: [10.0.1.221] => (item=mysql-server) 
skipping: [10.0.1.221]
changed: [10.0.1.182] => (item=nginx)
changed: [10.0.1.182] => (item=php)
changed: [10.0.1.182] => (item=php8.3-fpm)
changed: [10.0.1.182] => (item=mysql-server)

TASK [start services on Ubuntu server] ****************************************************************************************************************************
skipping: [10.0.1.221] => (item=nginx) 
skipping: [10.0.1.221] => (item=php8.3-fpm) 
skipping: [10.0.1.221] => (item=mysql) 
skipping: [10.0.1.221]
ok: [10.0.1.182] => (item=nginx)
ok: [10.0.1.182] => (item=php8.3-fpm)
ok: [10.0.1.182] => (item=mysql)

TASK [install LEMP on Amazon Linux server] ************************************************************************************************************************
skipping: [10.0.1.182] => (item=nginx) 
skipping: [10.0.1.182] => (item=php) 
skipping: [10.0.1.182] => (item=mariadb105-server) 
skipping: [10.0.1.182]
changed: [10.0.1.221] => (item=nginx)
changed: [10.0.1.221] => (item=php)
changed: [10.0.1.221] => (item=mariadb105-server)

TASK [start services on Amazon Linux server] **********************************************************************************************************************
skipping: [10.0.1.182] => (item=nginx) 
skipping: [10.0.1.182] => (item=php-fpm) 
skipping: [10.0.1.182] => (item=mariadb) 
skipping: [10.0.1.182]
changed: [10.0.1.221] => (item=nginx)
ok: [10.0.1.221] => (item=php-fpm)
changed: [10.0.1.221] => (item=mariadb)

PLAY RECAP ********************************************************************************************************************************************************
10.0.1.182                 : ok=4    changed=2    unreachable=0    failed=0    skipped=3    rescued=0    ignored=0   
10.0.1.221                 : ok=4    changed=2    unreachable=0    failed=0    skipped=3    rescued=0    ignored=0   
```
