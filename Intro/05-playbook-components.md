# Ansible Concepts: Playbook, Play, Modules, Tasks
## Playbook
A Playbook is a YAML file that defines a series of actions to be executed on managed nodes. It contains one or more "plays" that map groups of hosts to roles.

Example
---
```
---
- name: Setup all the required packages/softwares to run an Angular application
  hosts: my_instances
  become/remote_user: true/root
  tasks:
    - name: Update APT package index
      ansible.builtin.apt:
        update_cache: yes

    - name: Install nodejs
      ansible.builtin.apt:
        name: nodejs
        state: present

    - name: Install npm
      ansible.builtin.apt:
        name: npm
        state: present

    - name: Install Angular CLI
      ansible.builtin.npm:
        name: '@angular/cli'
        global: yes
        state: present
```
## Play
A Play is a single, complete execution unit within a playbook. It specifies which hosts to target and what tasks to execute on those hosts. Plays are used to group related tasks and execute them in a specific order.
```
- name: Setup all the required packages/softwares to run an Angular application
  hosts: my_instances
  become/remote_user: true/root
  tasks:
    - name: Install nodejs
      ansible.builtin.apt:
        name: nodejs
        state: present
```
## Modules
Modules are the building blocks of Ansible tasks. They are small programs that perform a specific action on a managed node, such as installing a package, copying a file, or managing services. 
Example The apt module used in a task to install a package:
```
- name: Install nodejs
  `ansible.builtin.apt:`
    name: nodejs
    state: present
```
## Tasks
Tasks are individual actions within a play that use modules to perform operations on managed nodes. Each task is executed in order and can include conditionals, loops, and handlers.
```
- name: Install nodejs
  ansible.builtin.apt:
    name: nodejs
    state: present

- name: Install npm
  ansible.builtin.apt:
    name: npm
    state: present
```
