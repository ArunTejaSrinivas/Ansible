# Ansible some usefull information

### ad hoc command
* ansible: Ad-hoc command for executing single tasks on managed nodes.
```
ansible -i inventory.ini all -m shell -a "touch /path/to/file"
```

* ansible-playbook: Runs Ansible playbooks, which contain multiple tasks.
```
ansible-playbook -i inventory my-playbook.yml
```
## Modules
Modules are the building blocks of Ansible tasks. Here are some commonly used modules:

### File Management:
* copy: Copy files from local machine to remote nodes.
* file: Manage file permissions, ownership, and symlinks.
* template: Apply Jinja2 templating to files.

### Package Management:
* apt: Manage packages on Debian/Ubuntu systems.
* yum: Manage packages on RedHat/CentOS systems.
* dnf: Manages packages on Fedora systems.

### Service Management:
* service: Start/stop/restart services.
* systemd: Manage systemd services.

### Networking:
* ping: Test connectivity between nodes.
* uri: Interact with HTTP services.

### Cloud Management:
* amazon.aws.ec2: Manage EC2 instances in AWS.
* amazon.aws.s3_bucket: Manage S3 buckets in AWS.

### Shell Commands:
* command: Run commands on remote nodes.
* shell: Execute shell commands on remote nodes.

  ## reqired for ansible

* ssh :
* ubuntu@Arunteja:~/ansible$ ls ~/.ssh
* ls: cannot access '/home/ubuntu/.ssh': No such file or directory
* ubuntu@Arunteja:~/ansible$ ls -al ~/.ssh
* ls: cannot access '/home/ubuntu/.ssh': No such file or directory

* if we observe like this that means ssh is not exit so we have run the command called :
* ssh-keygen 
*it will genereate : 
  * id_rsa (the private key)
  * id_rsa.pub (the public key)


### Check Python 3 version
python3 --version

### Check Python 2 version
python --version

### Install Python 3 if not installed
sudo apt update
sudo apt install python3

### Install pip for Python 3
sudo apt install python3-pip

### Verify installation
python3 --version
pip3 --version

### Uninstall Python 3
sudo apt remove python3

### Remove Python 3 and related packages completely
sudo apt purge python3
sudo apt autoremove

### Uninstall Python 2
sudo apt remove python

### Remove Python 2 and related packages completely
sudo apt purge python
sudo apt autoremove

### Uninstall Ansible installed via pip
pip uninstall ansible

### Uninstall Ansible installed via apt
sudo apt remove ansible

### Remove Ansible and related packages completely
sudo apt purge ansible
sudo apt autoremove

### Install Ansible
pip install ansible

### Check version
ansible --version
