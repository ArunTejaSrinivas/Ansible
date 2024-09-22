# Ansible
---
- name: Setup all the required packages/softwares to run an Angular application
  hosts: my_instances
  become: true

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

    - name: Clone code from GitHub repository
      ansible.builtin.git:
        repo: 'https://github.com/ArunTejaSrinivas/Angular-Project.git'
        dest: /home/ubuntu/Angular/Angular-Project

    - name: Install project dependencies
      ansible.builtin.npm:
        path: /home/ubuntu/Angular/Angular-Project
        state: present

    - name: Run Angular application in the background
      shell: nohup ng serve --host 0.0.0.0 --port 4200 --disable-host-check > /home/ubuntu/Angular/Angular-Project/nohup.out 2>&1 &
      args:
        chdir: '/home/ubuntu/Angular/Angular-Project'

    - name: Wait for Angular application to start
      wait_for:
        host: "{{ my_instances }}"
        port: 4200
        delay: 5
        timeout: 120
      tags: wait

    - name: Allow traffic on port 4200
      ufw:
        rule: allow
        port: 4200
        proto: tcp
      tags: firewall
