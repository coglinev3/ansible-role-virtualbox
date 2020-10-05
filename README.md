# Ansible Role: virtualbox

[![Build Status](https://travis-ci.org/coglinev3/virtualbox.svg?branch=master)](https://travis-ci.org/coglinev3/virtualbox) ![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/coglinev3/virtualbox) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://raw.githubusercontent.com/coglinev3/virtualbox/master/LICENSE)

This Ansible role installs Oracle VirtualBox on these supported Linux distributions:

* Debian 8 (Jessie),
* Debian 9 (Stretch),
* Debian 10 (Buster),
* Enterprise Linux 6, 
* Enterprise Linux 7, 
* Enterprise Linux 8, 
* Fedora 31,
* Fedora 32,
* Linux Mint 20 Ulyana,
* Ubuntu 14.04 LTS (Trusty Tahr),
* Ubuntu 16.04 LTS (Xenial Xerus),
* Ubuntu 18.04 LTS (Bionic Beaver),
* Ubuntu 20.04 LTS (Focal Fossa),

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

# define VirtualBox Version
vbox_version: 6.1
vbox_package: "virtualbox-{{ vbox_version }}"
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

Release: 1.1.0


## License

BSD


## Author Information

This Ansible Role was created in 2019, by Cogline.v3.
