# user

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/user/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/user.svg?branch=master)](https://travis-ci.org/ansiblebit/user)

[![Platform](http://img.shields.io/badge/platform-amazon-ff9900.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-debian-a80030.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-centos-932279.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-fedora-3c6eb4.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-freebsd-ae0000.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-macosx-000000.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-mint-87cfbe.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-opensuse-73ba25.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-redhat-cc0000.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-sles-73ba25.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-smartos-487487.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-windows-004185.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-user/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-user/)

[Ansible][ansible] to setup user accounts.


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#)  |
| Debian | Ubuntu  | Trusty  | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| Debian | Ubuntu  | Vivid   | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| RedHat | CentOS  | 6.4     | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| RedHat | CentOS  | 6.6     | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| RedHat | Centos  | 7       | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| RedHat | Fedora  | 20      | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |
| RedHat | Fedora  | 21      | [![x86](http://img.shields.io/badge/x86-n/a-cccccc.svg?style=flat)](#) [![x86_64](http://img.shields.io/badge/x86_64-n/a-cccccc.svg?style=flat)](#) |


## Requirements

- [ansible][ansible] >= 2.0


## Role Variables

- **debug**: flag to run debug tasks.

- **system_ssh_dir_public_keys**: directory where SSH public keys are stored.
- **system_ssh_dir_deprecated_keys**: directory where SSH deprecated public keys are stored.
- **system_groups**: system's groups.
- **system_ssh_deprecated_keys**: list of SSH keys that have been deprecated.
- **system_users**: system's user accounts.


## Dependencies

None.


## Playbooks

    - hosts: servers
      roles:
         - role: ansiblebit.user


## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
- **validation**: task to validate role variables.

- **system_authorized_keys**: 
- **system_debug**: 
- **system_group**: 
- **system_user**: 


## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```
$ tox
```

To run tests for `trusty64`:

```
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```


