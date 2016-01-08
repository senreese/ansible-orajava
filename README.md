# Ansible for Oracle Java

This should be an easy drop in role for anybody looking to get Oracle Java on to a machine.

General Info
--------------
Here it is. Plain old YAML. Easy.

Requirements
--------------
Ansible 2.x


Variables
--------------
In the defaults/main.yml file you will find some variables. These are used to construct
the various command lines. As it is, you'll get 1.8.66 (Thats SDK8u66 build17)

Feel free to edit that file, or to override it when you use this role in your playbook
with explicit vars.

Some are not used and are present for future additions. You'll live.

To Do
--------------
I will split the tasks/main.yml so that main only performs a check, and an include
to run if the check fails. That way if you have Java already, it will skip the
remainder of the tasks. This is a feature I was very disappointed to find in every other
playbook I could find: They just download and install JAvA over and over... wasteful.


Example
--------------
```
---
- hosts: test-hosts
  remote_user: ansible
  become: yes
  become_method: sudo
  roles:
    - orajava
```
