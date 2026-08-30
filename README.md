# [Ansible role ansible-generator](#ansible-generator)

Configure mounts on your system

|GitHub|Downloads|Version|
|------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml/badge.svg)](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml)|[![downloads](https://img.shields.io/ansible/role/d/mullholland/ansible-generator)](https://galaxy.ansible.com/mullholland/ansible-generator)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-ansible-generator.svg)](https://github.com/mullholland/ansible-role-ansible-generator/releases/)|
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  gather_facts: true
  vars:
    mount_requests:
      - path: "/mnt/tmp"
        mode: "1777"
        src: "/tmp"
        fstype: "none"
        opts: "bind"

  roles:
    - role: "{{ lookup('env', 'MOLECULE_PROJECT_DIRECTORY') }}"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/defaults/main.yml):

```yaml
---
# Mount dependencies like nfs-client-tools must be installed seperately
mount_requests: []
# mount_requests:
#   - path: "/mnt/backups"       # Required
#     owner: "root"              # Optional (Default 'root')
#     group: "root"              # Optional (Default 'root')
#     mode: "0750"               # Optional (Default '7500')
#     src: "10.0.0.10:/backups"  # Optional (Default 'omit')
#     boot: "true"               # Optional (Default 'omit')
#     fstype: "nfs"              # Optional (Required when state is present or mounted.)
#     opts: "defaults"           # Optional (Default 'omit')
#     dump: "0"                  # Optional (Default 'omit')
#     pass: "0"                  # Optional (Default 'omit')
#     state: "mounted"           # Optional (Default 'mounted')
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/mullholland/enterpriselinux)|all|
|[Rocky](https://hub.docker.com/r/mullholland/rockylinux)|all|
|[AlmaLinux](https://hub.docker.com/r/mullholland/almalinux)|all|
|[Amazon](https://hub.docker.com/r/mullholland/amazonlinux)|all|
|[Fedora](https://hub.docker.com/r/mullholland/fedora/)|all|
|[Ubuntu](https://hub.docker.com/r/mullholland/ubuntu)|all|
|[Debian](https://hub.docker.com/r/mullholland/debian)|all|
|[CentOS](https://hub.docker.com/r/mullholland/centos)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The version before the previous version.
- The previous version.
- The current version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-ansible-generator/issues).

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)
