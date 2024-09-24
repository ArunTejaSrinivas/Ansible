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
