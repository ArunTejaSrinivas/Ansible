What is Ansible ?

Ansible is an open source, command-line IT automation software application written in Python, that automates
-> provisioning :  Automatically creating cloud resources like EC2 instances, databases, load balancers, and networks in environments like AWS, Azure, or Google Cloud.
-> configuration management : For example, setting up users, services, or installing software packages across servers.
-> application deployment : Automate deploying and updating applications on multiple servers.
  and many other processes.


How Ansible works ?
* Ansible is agentless in nature, which means you don't need to install any software on the manage nodes.
* Ansible operates in a client-server architecture, where the control node (master machine) manages the managed nodes (client machines or servers).
   ->  Control Node: The machine where Ansible is installed and from which you execute the commands.
   ->  Managed Nodes: These are the remote systems (servers, switches, cloud resources) that Ansible manages. They don't require any agent, just SSH access or Windows Remote Management (WinRM) for Windows.
