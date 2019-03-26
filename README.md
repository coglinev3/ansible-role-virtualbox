# Ansible Role: virtualbox


This Ansible role installs Oracle VirtualBox on these supported Linux distributions:

* Enterprise Linux 6, 
* Enterprise Linux 7, 
* Ubuntu 14.04 LTS (Trusty Tahr),
* Ubuntu 16.04 LTS (Xenial Xerus),
* Ubuntu 18.04 LTS (Bionic Beaver),
* Ubuntu 18.10 (Cosmic Cuttlefish),
* Debian 8 (Jessie) and
* Debian 9 (Stretch).


## Requirements

None


## Role Variables

Available variables are listed below, along with default values:

```yml

# variables for Oracle's signing key
oracle_public_key: https://www.virtualbox.org/download/oracle_vbox_2016.asc
oracle_public_key_id: 2980AECF
oracle_public_key_state: present

# define package dependencies
vbox_dependencies:
  - apt-transport-https

# define VirtualBox Version
vbox_package: virtualbox-6.0
vbox_package_state: latest

# define VirtualBox users
vbox_users: []
```


## Dependencies

None


## Example Playbook

```yml
---
# file: tests/test.yml

- hosts: localhost
  become: true
  vars:
    vbox_users:
      - myaccount
  roles:
    - { role: coglinev3.virtualbox }
```


## Version

Release: x.y.z


## License

BSD


## Author Information

This Ansible Role was created in 2019, by Cogline.v3.
