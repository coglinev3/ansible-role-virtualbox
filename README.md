# Ansible Role: virtualbox

[![Build](https://github.com/coglinev3/ansible-role-virtualbox/actions/workflows/build.yml/badge.svg)](https://github.com/coglinev3/ansible-role-virtualbox/actions/workflows/build.yml) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/coglinev3/virtualbox) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://raw.githubusercontent.com/coglinev3/virtualbox/master/LICENSE)

This Ansible role installs Oracle VirtualBox on these supported Linux distributions:

* Debian 9 (Stretch),
* Debian 10 (Buster),
* Debian 11 (Bullseye),
* Enterprise Linux 7, 
* Enterprise Linux 8, 
* Enterprise Linux 9, 
* Fedora 35,
* Fedora 36,
* Linux Mint 20 Ulyana,
* Ubuntu 18.04 LTS (Bionic Beaver),
* Ubuntu 20.04 LTS (Focal Fossa),
* Ubuntu 22.04 LTS (Jammy Jellyfish),

This Role was tested with [Travis CI](https://travis-ci.org/coglinev3/virtualbox "Travis CI") using [Docker](https://www.docker.com/ "Docker") and  with a [multi virtual machine Vagrant environment](https://ansible-development.readthedocs.io "Environment for developing and testing Ansible roles").


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
  - build-essential
  - dkms

# define VirtualBox Version, package name, package state
vbox_version: "7.0"
vbox_package: "virtualbox-{{ vbox_version }}" on Debian or "VirtualBox-{{ vbox_version }}" on RedHat
vbox_package_state: latest

# define VirtualBox users
vbox_users: []

# Set debian or ubuntu release name (for example: stretch, buster, eaon, focal)
# If the variable is not set, Ansible will automatically determine the release.
debian_ubuntu_release: ""
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

Release: 1.1.2


## License

BSD


## Author Information

Copyright &copy; 2020 Cogline.v3.
