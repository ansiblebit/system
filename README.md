# system

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/system/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/system.svg?branch=master)](https://travis-ci.org/ansiblebit/system)

[![Platform](http://img.shields.io/badge/platform-debian-a80030.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-centos-932279.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-fedora-3c6eb4.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-opensuse-73ba25.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-redhat-cc0000.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-system/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-system/)

[Ansible][ansible] to setup user groups, user accounts and authorized keys.


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian   | Wheezy     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Debian   | Jessie     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Yakkety    | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Xenial     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Wily       | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Vivid      | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Trusty     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu   | Precise    | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Suse   | OpenSUSE | Leap       | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Suse   | OpenSUSE | Tumbleweed | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | CentOS   | 7          | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | CentOS   | 6          | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | Fedora   | 21         | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | Fedora   | 20         | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


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
         - role: ansiblebit.system


## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
- **validation**: validation tasks.

- **system_authorized_keys**: authorized keys setup tasks.
- **system_debug**: role specific debug tasks.
- **system_group**: group setup tasks.
- **system_user**: user setup tasks.
- **system_validation**: role specific validation tasks.


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

[ansible]:  https://ansible.com/    "Ansible"
