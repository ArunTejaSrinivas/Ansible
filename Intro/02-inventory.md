# Inventory
Ansible inventory file is a fundamental component of Ansible that defines the hosts (remote systems) that you want to manage and the groups those hosts belong to. It provides Ansible with the information about the remote nodes to communicate with during its operations.

## INI Format
```
#inventory file: hosts

[webservers]
web1.example.com
web2.example.com

[dbservers]
db1.example.com
db2.example.com
```
