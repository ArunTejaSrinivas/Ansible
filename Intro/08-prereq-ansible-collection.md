# Setup EC2 Collection and Authentication
## Install boto3
```
pip install boto3
```
## Install AWS Collection
```
ansible-galaxy collection install amazon.aws
```
## Setup Vault
1) Create a password for vault
```
openssl rand -base64 2048 > vault.pass
```
2) Add your AWS credentials using the below vault command
```
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass
```
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
` * id_rsa.pub (the public key)


# Check Python 3 version
python3 --version

# Check Python 2 version
python --version

# Install Python 3 if not installed
sudo apt update
sudo apt install python3

# Install pip for Python 3
sudo apt install python3-pip

# Verify installation
python3 --version
pip3 --version

# Uninstall Python 3
sudo apt remove python3

# Remove Python 3 and related packages completely
sudo apt purge python3
sudo apt autoremove

# Uninstall Python 2
sudo apt remove python

# Remove Python 2 and related packages completely
sudo apt purge python
sudo apt autoremove

# Uninstall Ansible installed via pip
pip uninstall ansible

# Uninstall Ansible installed via apt
sudo apt remove ansible

# Remove Ansible and related packages completely
sudo apt purge ansible
sudo apt autoremove

# Install Ansible
pip install ansible

# Check version
ansible --version


