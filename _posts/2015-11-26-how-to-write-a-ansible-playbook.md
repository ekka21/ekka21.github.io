---
id: 666
title: How to write a Ansible Playbook
date: 2015-11-26T19:17:14+00:00
author: ek
layout: post
guid: http://ekkachai.net/?p=666
permalink: /2015/11/26/how-to-write-a-ansible-playbook/
categories:
  - ansible
tags:
  - ansible playbook
---
When I write a playbook, I always think of:
  
1. create hosts or inventories

<pre>[lb]
198.163.33.10

[db]
198.163.33.20

[app]
198.163.33.31
198.163.33.32
198.163.33.33

</pre>

2. **Which** remote servers am I running against?

<pre>---
- hosts: app
  user: root
  sudo: yes
  gather_facts: yes
</pre>

4. **What** are my tasks?

<pre>tasks: 
    - name: Define your task name
      yum: name={{ item }} state=latest 
      with_items:
        - git
        - ntp
        - nginx
        - vim

    - name: Start ntp 
      service: name=ntpd state=started enabled=yes

    - name: Start nginx
      service: name=nginx state=started enabled=yes
      
    - name: Ensure mysql is installed
      yum: name={{ item }} state=present
      with_items:
        - mysql-server
        - MySQL-python
        - libselinux-python
        - libsemanage-python 

    - name: Start mysql service
      service: name=mysqld state=started enabled=yes
</pre>

Here is the overview of my playbook:

<pre>---
- hosts: web
  user: root
  sudo: yes
  gather_facts: yes

  tasks: 
    - name: Define your task name
      yum: name={{ item }} state=latest 
      with_items:
        - git
        - ntp
        - nginx
        - vim

    - name: Start ntp 
      service: name=ntpd state=started enabled=yes

    - name: Start nginx
      service: name=nginx state=started enabled=yes
      
    - name: Ensure mysql is installed
      yum: name={{ item }} state=present
      with_items:
        - mysql-server
        - MySQL-python
        - libselinux-python
        - libsemanage-python 

    - name: Start mysql service
      service: name=mysqld state=started enabled=yes
 
</pre>